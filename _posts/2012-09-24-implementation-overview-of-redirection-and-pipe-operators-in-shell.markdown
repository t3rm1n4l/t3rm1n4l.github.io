---
layout: post
status: publish
published: true
title: Implementation of redirection and pipe operators in shell
date: 2012-09-24 17:15:20.000000000 +05:30
categories:
- Articles
tags:
- linux
- bash
- unix
- design
- file descriptors
- pipe
- redirection
- shell
- fork
- exec
comments:
- id: 14698
  author: vish
  author_email: viswaug@yahoo.com
  author_url: ''
  date: '2013-02-11 19:07:20 +0530'
  date_gmt: '2013-02-11 19:07:20 +0530'
  content: "Hey,\r\n\r\nGreat info. Thank you for writing it up. I am a linux newbie
    and this explains a lot of things that are done on the command line. Can you shed
    some light on where the main function is executed? Is it in the child or the parent
    process? From the code, it looks like they both use&#47;share&#47;execute the
    same main function. I am going by the use of \"if(fork() ==0\". Is that the case?
    So, in that case the if block will be executed in the child process and the else
    block in the parent process?\r\n\r\nAgain, I appreciate the post very much.\r\n\r\nThank
    You,\r\nVish"
- id: 15739
  author: muky
  author_email: mukyman@hotmail.com
  author_url: ''
  date: '2013-05-23 09:11:22 +0530'
  date_gmt: '2013-05-23 09:11:22 +0530'
  content: "How would implement this pipe?\r\ncat &ndash;A > output.txt"
---
I have been always fascinated about the design of UNIX. I am still curious and enjoy the philosophy and the idea of 'Write programs that do one thing and do it well'. Aim of this blog post is to walk through some interesting aspects on implementation of file descriptors and to illustrate how gracefully that design helps to build interesting unix shell methodologies. For any process, there are three default file descriptors. Stdin - with descriptor number 0, Stdout - with descriptor number 1 and Stderr with descriptor number 2.

Let us go through some basic system calls. All the system calls explained below are not exact syntax. Please refer man for correct function prototype.

#### 1. fork()
The fork system call creates another copy of current process and mark the new process as child of parent process which called fork. This system call returns zero in the child process and return child's pid in the parent process. It copies everything including file descriptors, and virtual memory. If a process tries to write any virtual memory page, it will do a copy on write to create copy of that particular page for that process space.

#### 2. exec(binary_path)
The exec system call overwrites the current process with executable image from a file. Eg. if you run exec("/bin/ls"). It will overwrite the memory code image with binary from /bin/ls and execute. The file descriptor table remains the same as that of original process.

#### 3. open(file, mode)
Opens a file and creates a file descriptor associated with the file.

IMPORTANT: By design, when the kernel allocates a file descriptor, it will create the fd with next smallest available file descriptor number.

#### 4. close(fd)
Closes the open file descriptor

#### 5. dup(fd)
The dup system call creates a file descriptor that is duplicate of given fd passed as argument.

#### 6. pipe(int arr[2])
Creates a pipe, and stores the read descriptor in array location zero and write descriptor in array location one.

#### 7. read(fd, buff, len)
Reads len bytes to buff from file descriptor fd.

#### 8. write(fd, buff, len)
Writes len bytes from buff to file descriptor fd.

Let us go through some interesting shell features that we use frequently and look at their implementations.

## Redirections
<b>$ cmd1 > stdout.txt</b>

The above command redirects stdout to file stdout.txt

For implementing the above operation, we should be able to link stdout of cmd1 with file descriptor of stdout.txt opened with write mode.
Let us look at the code.

{% highlight bash linenos linenos %}
main(){
    close(1); // Release fd no - 1
    open("stdout.txt", "w"); // Open a file with fd no = 1
    // Child process
    if (fork() == 0) {

        exec("cmd1"); // By default, the program writes to stdout (fd no - 1). ie, in this case, the file
    }
}
{% endhighlight %}

<b>$ cmd1 2> stdout.txt</b>

The above command redirects stderr to file stdout.txt

{% highlight bash linenos linenos %}
main(){
    close(2); // Release fd no - 2
    open("stderr.txt", "w"); // Opens file with fd no - 2
    // Child process
    if (fork() == 0) {
        exec("cmd1"); // Writes to stderr (fd no 2)
    }
}
{% endhighlight %}

<b>$ cmd2 > stdout_stderr.txt 2>&1</b>

The above command redirects both stdout and stderr to file stdout_stderr.txt

{% highlight bash linenos linenos %}
main(){
    close(1); // Release fd no - 1
    open("stdout_stderr.txt", "w"); //Opens file with fd no - 1
    // Child process
    if (fork() == 0) {
        close(2); // Release fd no - 2
        dup(1); // Create fd no - 2 which is duplicate of fd no -1. Hence, we joined fd 1 and 2 (stdout and  stderr)
        exec("cmd2");
    }
}
{% endhighlight %}

<b>$ cmd3 < input.txt</b>

The above command redirects data from input.txt to stdin for cmd3.

{% highlight bash linenos linenos %}
main(){
    close(0);//Release fd - 0
    open("stdout.txt", "r"); //Open file with fd - 0

    //Child process
    if (fork() == 0) {
        exec("cmd3"); // By default, program reads from stdin. ie, fd - 0
    }
}
{% endhighlight %}

## Pipe
<b>$ cmd1 | cmd2 </b>

This command says that cmd2 will receive stdin from stdout of cmd1.

{% highlight bash linenos linenos %}
main(){
    int p[2];
    pipe(p); // Creates a pipe with file descriptors Eg. input = 3 and output = 4 (Since, 0,1 and 2 are not available)

    if (fork() == 0) {
    // Child process
        close(0); // Release fd no - 0
        close(p[0]); // Close pipe fds since useful one is duplicated
        close(p[1]);
        dup(p[0]); // Create duplicate of fd - 3 (pipe read end) with fd 0.
        exec("cmd2");
    } else {
        //Parent process
        close(1); // Release fd no - 1
        close(p[0]); // Close pipe fds since useful one is duplicated
        close(p[1]);
        dup(p[1]); // Create duplicate of fd - 4 (pipe write end) with fd 1.
        exec("cmd1");
    }
}
{% endhighlight %}

Aren't you feeling awesome?
With simple design, without making any code change to individual programs, it is possible to connect input and output streams to individual programs. Hats off to designers of UNIX.

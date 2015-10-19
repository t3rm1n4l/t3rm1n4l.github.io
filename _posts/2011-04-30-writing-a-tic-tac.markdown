---
layout: post
status: publish
published: true
title: Writing a Tic Tac Toe program using AI (Minimax)
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
excerpt: "<img src=\"http://farm3.static.flickr.com/2732/4250653771_66c65ba064.jpg\"
  alt=\"tic-tac-toe\" width=\"400px\"/>\r\n\r\nMost of us know the <a href=\"http://en.wikipedia.org/wiki/Tic-tac-toe\">Tic-Tac-Toe</a>
  game. If not, you might know this game in another name. I belonged to the second
  category. I had played this game many times in my childhood but with another localised
  name. This game said to be a simplest example of programming with a game tree. Tic-Tac-Toe
  also seems to be a common interview coding question for Software Engineer - Developer
  positions.\r\n\r\nLet me give a brief idea of what is this game about. It consits
  of a board containing 9 cells with 3x3 (rowxcolumn). It is a two player game with
  each player assigned with a marker symbol (X or O). During the first turn the player
  mark the symbol X (Marker symbol corresponding to the player) to a cell among the
  available cells, and the second player will mark O (Second player's symbol) to a
  cell among the available cells. The game continues until it reaches either one of
  the conditions:\r\nWhen one column, row or diagonal has X, The player assigned with
  X wins else if this state arrived for O, the player O wins. If the board contains
  no free cell left and none of the above conditions arrived, the Game ends with Draw."
wordpress_id: 999
wordpress_url: http://www.sarathlakshman.com/?p=999
date: 2011-04-30 02:54:43.000000000 +05:30
categories:
- General
- Hacks
- Interview
tags:
- python
- interview
- code
- tic-tac-toe
- gametree
- artifiical intelligence
- program
- gaming
comments:
- id: 11345
  author: navmad
  author_email: navmad@gmai.com
  author_url: ''
  date: '2011-04-30 05:31:40 +0530'
  date_gmt: '2011-04-30 05:31:40 +0530'
  content: Kewl one dude... :-D... Give this link to JJ..
- id: 11392
  author: khareen
  author_email: kharenjam@gmail.com
  author_url: http://yourabs.org
  date: '2011-05-23 10:10:19 +0530'
  date_gmt: '2011-05-23 10:10:19 +0530'
  content: "@navmad:\r\n\r\nAre you a programmer too?\r\n\r\n\"Python\" is kinda not
    my type but i will try it."
- id: 11454
  author: robinthapa
  author_email: librain.robin@gmail.com
  author_url: http://gravatar.com/robinthapa
  date: '2011-06-16 12:09:24 +0530'
  date_gmt: '2011-06-16 12:09:24 +0530'
  content: Do you have it in Java
- id: 11653
  author: Jyoti
  author_email: jyoti.salimath3@gmail.com
  author_url: ''
  date: '2011-08-25 10:51:49 +0530'
  date_gmt: '2011-08-25 10:51:49 +0530'
  content: "Hi, I want c code for tic tac toe game \r\nfor two player of human and
    two player of one human and another is AI."
- id: 11682
  author: Kalyan
  author_email: nvsnkalyan@gmail.com
  author_url: http://kalyanchakravarthy.net
  date: '2011-09-11 04:23:16 +0530'
  date_gmt: '2011-09-11 04:23:16 +0530'
  content: Neat!!
- id: 11685
  author: Bushra
  author_email: bushyfawas@gmail.com
  author_url: ''
  date: '2011-09-13 15:10:17 +0530'
  date_gmt: '2011-09-13 15:10:17 +0530'
  content: "do u know to explain the 1st algorithm for tic-tac toe in BOOk Artificial
    Intelligence by Rich &amp; Knight\r\n."
- id: 11699
  author: Bruno
  author_email: beankill@gmail.com
  author_url: ''
  date: '2011-09-26 13:50:33 +0530'
  date_gmt: '2011-09-26 13:50:33 +0530'
  content: "Nice. I've had horrible AI classes, so I've never heard of MINMAX algoritm.
    It's a nice idea, but it takes large cpu, tought.\r\n\r\n@Jyoti\r\nAre you kidding?
    He gives you the code, with a nice documentation. Just read it and code the same
    thing in C."
- id: 12131
  author: dewa
  author_email: real_baladewa2000@yahoo.com
  author_url: http://simplewrote.wordpress.com
  date: '2012-04-12 18:14:56 +0530'
  date_gmt: '2012-04-12 18:14:56 +0530'
  content: "hi. Very clean write. I like your explanation. But i don't get when we
    called minimize function?\r\n\r\nif this right? we called move(). In this move()
    we called maxMove(). Then check the winning condition. If not win yet we called
    minMove function?\r\n\r\nand how we get score for every moves? you said we give
    1,0 and -1, how actually we do that? are the condition is rules by programer or
    there's a special math formula in minimax?\r\n\r\nthanx for your respond :)"
- id: 12188
  author: rohit
  author_email: d@d.com
  author_url: ''
  date: '2012-05-05 14:05:49 +0530'
  date_gmt: '2012-05-05 14:05:49 +0530'
  content: "dude u r going well ,,,, these guys need a algo not code,,\r\n\r\npython
    rocks ,, even if i dont understand code :)"
- id: 12251
  author: Tic. Tac. Toe. &laquo; Rylan Dirksen
  author_email: ''
  author_url: http://rylandirksen.wordpress.com/2012/05/21/tic-tac-toe/
  date: '2012-05-21 23:40:52 +0530'
  date_gmt: '2012-05-21 23:40:52 +0530'
  content: '[...] friend Mike and asked him for thoughts. He suggested I visit a few
    sites and compare my code to what others had done (without stealing!) just to
    see where I was at. Honestly, the code I looked at didn&#8217;t help me [...]'
- id: 12359
  author: r
  author_email: agrawal.rohan@gmail.com
  author_url: ''
  date: '2012-06-18 18:26:00 +0530'
  date_gmt: '2012-06-18 18:26:00 +0530'
  content: "Hi sarath\r\n\r\nI modified your code to pit the AI vs AI, and gave a
    starting scenario.\r\n\r\nThe results were somewhat unexpected. The first turn
    belongs to 'O' and I am somewhat surprised that O choose to move where it did,
    and not in the middle to prevent X completing a diagonal win. I know that even
    that move, would not prevent O from a loss, but still.\r\n\r\nCurrent board:\r\nX
    | - | - |\r\n- | - | - |\r\nO | - | X |\r\n                [Computer's Move]\r\n\r\nCurrent
    board:\r\nX | O | - |\r\n- | - | - |\r\nO | - | X |\r\n                [Computer's
    Move]\r\n\r\nCurrent board:\r\nX | O | X |\r\n- | - | - |\r\nO | - | X |\r\n                [Computer's
    Move]\r\n\r\nCurrent board:\r\nX | O | X |\r\nO | - | - |\r\nO | - | X |\r\n                [Computer's
    Move]\r\n\r\nCurrent board:\r\nX | O | X |\r\nO | X | - |\r\nO | - | X |\r\n\r\nWinner
    : X"
- id: 13002
  author: Reply to r
  author_email: kvvaysage@gmail.com
  author_url: ''
  date: '2012-09-29 16:45:10 +0530'
  date_gmt: '2012-09-29 16:45:10 +0530'
  content: "Hi r,\r\n  The problem is with the scoring function.(get_score).\r\nModify
    it .\r\nIst way:\r\n----------- \r\n Modify it go give a score of anything greater
    than +Infinity if current player wins OR anything lesser than -Infinityif other
    player wins .while returning do --score if current player OR ++score if other
    player.\r\n\r\nIInd way:\r\n-----------\r\nModify score function to give a score
    according to the present move number.i.e just give  score = Infinity - movenumber
    if current player wins .Give score = -Infinity + movenumber if other player wins.\r\n\r\nNote:
    Infinity  can be anything more than 5. \r\nNote: Current player =  Maxplayer &amp;&amp;
    other player =Minplayer"
- id: 14900
  author: 5agado
  author_email: sagado91@yahoo.it
  author_url: ''
  date: '2013-04-14 16:35:33 +0530'
  date_gmt: '2013-04-14 16:35:33 +0530'
  content: "Wonderful solution!\r\nA lot simpler than all the others than I found
    on the web, but equally operative.\r\n\r\nThanks so much for the sharing of the
    code.\r\nFor everyone interested here(github.com/5agado/android-TicTacToe/tree/master/TicTacToe)
    you can find my implementation of the game for android."
---
<img src="http://farm3.static.flickr.com/2732/4250653771_66c65ba064.jpg" alt="tic-tac-toe" width="400px"/>

Most of us know about [tic tac toe][tick_tac_toe] game. If not, you might know this game in another name. I belonged to the second category. I had played this game many times in my childhood but with another localised name. This game said to be a simplest example of programming with a game tree. Tic-Tac-Toe also seems to be a common interview coding question for Software Engineer - Developer positions.

Let me give a brief idea of what is this game about. It consits of a board containing 9 cells with 3x3 (rowxcolumn). It is a two player game with each player assigned with a marker symbol (X or O). During the first turn the player mark the symbol X (Marker symbol corresponding to the player) to a cell among the available cells, and the second player will mark O (Second player's symbol) to a cell among the available cells. The game continues until it reaches either one of the conditions: When one column, row or diagonal has X, The player assigned with X wins else if this state arrived for O, the player O wins. If the board contains no free cell left and none of the above conditions arrived, the Game ends with Draw.

Now, Our goal is to write a program to play this Tic-Tac-Toe. First we will write a program conists of Human-Human player game such that it can played between two friends. After writing Human-Human game, we can improve it by replacing one Human player with Artificial Intelligent Player. Writing an Artificial Intelligent Player is the most interesting part of the code.

Artifical Intelligence was one of my subjects in the Semester-8. Since I did not study MiniMax theorem in AI for examination because of the fact that the last minute study didn't work. While writing the AI player program, I went through the MiniMax theorem and found it very interesting unlike classroom. I will describe more in the later part of this post. The AI player is a simplest application of MiniMax theorem. If teachers could show Tic-Tac-Toe program in the AI classroom, it would have simplified the task of teaching without leaving any complexity.

The complete code for the Tic-Tac-Toe in python is given below. Explanation for the components in the program are described as below.

### GAME class
It consists of a class GAME. It is the major class which contains the states and methods required for the game. Initially it sets all the cells in the board (self.board) with '-' (blank). An empty list, lastmoves is initialized. self.lastmoves is a stack which consists of recently marked positions. It consists of print_board() function which is used to print the cells in the current board. get_free_positions() return a list of unmarked positions on the board. mark() function marks a position with a marker symbol. When it marks a position, it pushes that position to the lastmoves stack.

The revert_last_move() function reset the recent move (Recent marking). It makes use of lastmoves stack for resetting the last move by unmarking it.

The is_gameover() function returns True or False based on whether game is completed or not. A game completes when either of the players win or when the game reaches Draw. win_pos list consists of eight different three-cell combinations that corresponds to winning state. ie (first row, second row, third row, first col, second col, third col and two diagonals). This method sets the self.winner when game is over.

The play() method executes the game play. It takes two player objects as arguments. Each player has a method move() which performs that player's move. Since there are nine cells in the game board, it executes the loop for a maximum of nine times. It calls the move() method for each of the players alternatively. On each move, it checks whether the game is completed or not. 


We have two player classes Human and AI used in this program. Actually we can create a Base class Player and inherit child player classes, AI and Human and implement move() method individually. (Good OOP design). But I haven't used any base class and inheritance to leave the code simple.

### Human class - The Human player
Human class is a player attribute used in the play() function of GAME class. It has a constructor (__init__() ) and a method move(). When the object is initialized, it sets the marker for the player as self.marker = "X" and sets type of player (Human(H) or Computer(C)). Human class is meant for Human player. The move() function takes an instance of GAME class (current game). The method reads the next move position from the user and marks the position with player marker (X or O) if it is available.

See the lines which is at the end of the lines in the program:
   player1 = Human("X")
   player2 = AI("O")

Now replace player2 as Human (player2 = Human("O")) and execute the script. Now you have a two player Human-Human game. Try a game with your friend.

Next target is to code an Artificial Intelligent Player.

### AI class - The computer player
We use our brain logic to play Tic Tac Toe game. Everybody plays to win the game. How do we code up an intelligent Player which plays to win. Winning can be achieved by foreseeing the moves of the opponent. If we can foresee all the possible moves of opponent until the end of the game, we can always choose the best move. That should be the basic idea of the intelligent program. Foresee or emulate the next states of game. The technique used for foreseeing and choosing the best move is called MiniMax theorem.

The AI class is similar to Human class. It consists of similar initialization part. But AI class has an additional attribute called opponentmarker which stores the marker for the opponent, which will be used for emulate marking of opponent. The AI class consists of the following methods:
move() - Chooses the next move
maximized_move() - returns the next best move (To reach winning game end)
minimized_move() - returns the next best move for opponent (Means worst move for current player) 
get_score() - returns the status of game on end. Win, lose or draw.

The move() method calls maximized_move() which returns the best move position and marks that cell as next move.
The get_score() function checks whether game has ended. If ended, it returns 1 if the AI player won, -1 if other player won or 0 if draw. These values are scores.

The major players of minimax theorem are Max functioning and Min functioning. Max function maximizes the possibility of win and Min function minimizes. Let us see what is written in the maximized_move().
It gets a list of all available moves and apply the moves one by one. Check if game has ended, if it is ended collect the score and check whether it is better than all moves applied, if it is the best one use that as bestmove. If game has not ended, call minimized_move() so that next opponent's move is emulated.

The minimize_move() method does exactly same as maximized_move(), except it selects the worst score as best move. (That means, -1 score means opponent win, which is the best case for opponent. In minimize, we are emulating the best move of opponent). The minimized_move() calls maximized_move() for emulating the next state (The AI player's state). 

Hence once maximized is called, it will execute a stack of Max-Min-Max-Min-Max.. until the game over. In such way it find outs the best next move for the intelligent player. Hence we cannot beat the intelligent player. We can only defend until we reach a draw. At each state, it applies all the available moves and emulate the game with all possibilities to which it wins, and selects the best move. When the Max-Min-Max.. recursive call returns at each level, revert_last_move() method is used to reset the last move (Since it is an emulation and has to return to previous state after emulation outcome is obtained).

Now, try running the original program and play the game with Computer. After that change both players to AI and see what happens.

The given program applies Max-Min sequence until end of game for every move. It is very CPU expensive. If we need to reduce the intelligence to make it less CPU expensive, restrict the sequence of Max-Min calls to a restricted number of levels.


Hope you enjoy this post.

{% highlight python linenos linenos %}
#!/usr/bin/env python
#Filename: tic-tac-toe.py
#Description: Tic-Tac-Toe two player game

class GAME:

    def __init__(self):
        '''Initialize parameters - the game board, moves stack and winner'''

        self.board = [ '-' for i in range(0,9) ]
        self.lastmoves = []
        self.winner = None

    def print_board(self):
        '''Print the current game board'''
        
        print "\nCurrent board:"

        for j in range(0,9,3):
            for i in range(3):
                if self.board[j+i] == '-':
                    print "%d |" %(j+i),
                else:
                    print "%s |" %self.board[j+i],
    
            print "\n",


    def get_free_positions(self):
        '''Get the list of available positions'''

        moves = []
        for i,v in enumerate(self.board):
            if v=='-':
                moves.append(i)
        return moves

    def mark(self,marker,pos):
        '''Mark a position with marker X or O'''
        self.board[pos] = marker
        self.lastmoves.append(pos)

    def revert_last_move(self):
        '''Reset the last move'''

        self.board[self.lastmoves.pop()] = '-'
        self.winner = None

    def is_gameover(self):
        '''Test whether game has ended'''

        win_positions = [(0,1,2), (3,4,5), (6,7,8), (0,3,6),(1,4,7),(2,5,8), (0,4,8), (2,4,6)]

        for i,j,k in win_positions:
            if self.board[i] == self.board[j] == self.board[k] and self.board[i] != '-':
                self.winner = self.board[i]
                return True

        if '-' not in self.board:
            self.winner = '-'
            return True

        return False

    def play(self,player1,player2):
        '''Execute the game play with players'''

        self.p1 = player1
        self.p2 = player2
    
        for i in range(9):

            self.print_board()
            
            if i%2==0:
                if self.p1.type == 'H':
                    print "\t\t[Human's Move]"
                else:
                    print "\t\t[Computer's Move]"

                self.p1.move(self)
            else:
                if self.p2.type == 'H':
                    print "\t\t[Human's Move]"
                else:
                    print "\t\t[Computer's Move]"

                self.p2.move(self)

            if self.is_gameover():
                self.print_board()
                if self.winner == '-':
                    print "\nGame over with Draw"
                else:
                    print "\nWinner : %s" %self.winner
                return

class Human:
    '''Class for Human player'''

    def __init__(self,marker):
        self.marker = marker
        self.type = 'H'
    
    def move(self, gameinstance):

        while True:
        
            m = raw_input("Input position:")

            try:
                m = int(m)
            except:
                m = -1
        
            if m not in gameinstance.get_free_positions():
                print "Invalid move. Retry"
            else:
                break
    
        gameinstance.mark(self.marker,m)
         
class AI:
    '''Class for Computer Player'''

    def __init__(self, marker):
        self.marker = marker
        self.type = 'C'

        if self.marker == 'X':
            self.opponentmarker = 'O'
        else:
            self.opponentmarker = 'X'

    def move(self,gameinstance):
        move_position,score = self.maximized_move(gameinstance)
        gameinstance.mark(self.marker,move_position)



    def maximized_move(self,gameinstance):
        ''' Find maximized move'''    
        bestscore = None
        bestmove = None

        for m in gameinstance.get_free_positions():
            gameinstance.mark(self.marker,m)
        
            if gameinstance.is_gameover():
                score = self.get_score(gameinstance)
            else:
                move_position,score = self.minimized_move(gameinstance)
        
            gameinstance.revert_last_move()
            
            if bestscore == None or score > bestscore:
                bestscore = score
                bestmove = m

        return bestmove, bestscore

    def minimized_move(self,gameinstance):
        ''' Find the minimized move'''

        bestscore = None
        bestmove = None

        for m in gameinstance.get_free_positions():
            gameinstance.mark(self.opponentmarker,m)
        
            if gameinstance.is_gameover():
                score = self.get_score(gameinstance)
            else:
                move_position,score = self.maximized_move(gameinstance)
        
            gameinstance.revert_last_move()
            
            if bestscore == None or score < bestscore:
                bestscore = score
                bestmove = m

        return bestmove, bestscore

    def get_score(self,gameinstance):
        if gameinstance.is_gameover():
            if gameinstance.winner  == self.marker:
                return 1 # Won
            elif gameinstance.winner == self.opponentmarker:
                return -1 # Opponent won
        return 0 # Draw
        

if __name__ == '__main__':
    game=GAME()     
    player1 = Human("X")
    player2 = AI("O")
    game.play( player1, player2)

{% endhighlight %}

Thanks to the Tic-Tac-Toe image which is licensed under CC (source: <a href="http://www.flickr.com/photos/public-domain-photo/4250653771/sizes/l/in/photostream/">http://www.flickr.com/photos/public-domain-photo/4250653771/sizes/l/in/photostream/</a>). 

[tictactoe]: http://en.wikipedia.org/wiki/Tic-tac-toe

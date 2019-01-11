The screen program allows you to use multiple windows (virtual VT100 terminals) in Unix.

Note: UITS does not support screen.
Features

    If your local computer crashes or you lose the connection, the processes or login sessions you establish through screen don't go away. You can resume your screen sessions with the following command:

     screen -r

    In some cases you may have to manually "detach" your screen session before resuming it. For more information, see the Knowledge Base document Using screen, why can't I re-attach to my session after a lost connection?
    The screen program creates multiple processes instead of multiple Unix login sessions, which means that it is resource-efficient.
    You can cut and paste between different screens without using a mouse. Thus, you don't need to be on a computer with a windowing environment such as macOS, Windows, or the X Window System.
    It has a block copy feature which is similar to the kill rectangle feature of Emacs.
    You can copy and paste more than one page at a time, which you cannot do with some clients. You can scroll up more than one page, depending on how many scrolling lines you have set with the -h option.
    Using the detach feature, you can save screen processes when logging out and resume where you left off, saving the trouble of restarting them.

Starting screen

To start screen, enter the following command:

 screen

General commands

Note: Every screen command begins with Ctrl-a.
Ctrl-a c 	Create new window (shell)
Ctrl-a k 	Kill the current window
Ctrl-a w 	
List all windows (the current window is marked with "*")
Ctrl-a 0-9 	Go to a window numbered 0-9
Ctrl-a n 	Go to the next window
Ctrl-a Ctrl-a 	
Toggle between the current and previous window
Ctrl-a [ 	Start copy mode
Ctrl-a ] 	Paste copied text
Ctrl-a ? 	
Help (display a list of commands)
Ctrl-a Ctrl-\ 	Quit screen
Ctrl-a D (Shift-d) 	Power detach and logout
Ctrl-a d 	
Detach but keep shell window open

Press the Spacebar or Enter to end a command.
To copy a block

To get into copy mode, press Ctrl-a [ .

To move the cursor, press the h, j, k, and l (the letter l) keys. The 0 (the number 0) or ^ (the caret) moves to the start of the line and $ (the dollar sign) moves to the end of the line. Ctrl-b scrolls the cursor back one page and Ctrl-f scrolls forward one page. To set the left and right margins of copy, press c and C (Shift-c). The Spacebar starts selecting the text and ends selecting the text. To abort copy mode, press Ctrl-g.
To paste a block

To paste the copied text to the current window (as many times as you want), press Ctrl-a ].
Other commands

To run a program or execute any Unix command in a new window, at the Unix prompt, enter:

 screen unixcommand

Above, replace unixcommand with the appropriate command name.

To automatically start several windows when you run screen, create a .screenrc file in your home directory and put screen commands in it.

To quit screen (kill all windows in the current session), press Ctrl-a Ctrl-\.

The man pages for screen are quite readable and make a good tutorial. At the Unix prompt, enter:

 man screen

At Indiana University, for personal or departmental Linux or Unix systems support, see At IU, how do I get support for Linux or Unix?
Related documents
Using screen, why can't I re-attach to my session after a lost connection?


his guide will show you how to use the seq command to generate lists of numbers within the Linux terminal.
Basic Syntax Of The Seq Command

Imagine you wanted to display the numbers 1 to 20 to the screen.

The following seq command shows you how to do this:

seq 1 20

On its own, this command is fairly useless. At the very least you will want to output the numbers to a file.

You can do this using the cat command as follows:

seq 1 20 | cat > numberedfile

Now you will have a file called numberedfile with the numbers 1 to 20 printed on each line.

The method we have shown thus far for displaying a sequence of numbers could have been condensed to the following:

seq 20

The default start number is 1 so by just supplying the number 20 the seq command automatically counts from 1 to 20.

You only need to use the long format if you want to count between two different numbers as follows:

seq 35 45

This will display the numbers 35 through 45 to the standard output.
How To Set An Increment Using The Seq Command

If you want to show all the even numbers between 1 and 100 you can use the increment part of seq to step 2 numbers at a time as the following example shows:

seq 2 2 100

In the above command, the first number is the starting point. 

The second number is the number to increment by in each step, for example, 2 4 6 8 10.

The third number is the final number to count to.
Formatting The Seq Command

Simply sending numbers to the display or to a file isn't particularly useful.

However, maybe you want to create a file with every date in March.

To do this you can use the following switch:

seq -f "%02g/03/2016" 31

This will display output similar to the following:

    01/03/2016
    02/03/2016
    03/03/2016

You will notice the %02g. There are three different formats: e, f, and g. 

As an example of what happens when you use these different formats try the following commands:

seq -f "%e" 1 0.5 3
seq -f "%f" 1 0.5 3
seq -f "%g" 1 0.5 3

The output from the %e is as follows:

    1.000000e+00
    1.500000e+00
    2.000000e+00
    2.500000e+00
    3.000000e+00

The output from the %f is as follows:

    1.000000
    1.500000
    2.000000
    2.500000
    3.000000

Finally, the output from %g is as follows:

    1
    1.5
    2
    2.5
    3

Using The Seq Command As Part Of A For Loop

You can use the seq command as part of a for loop to run through the same code a set number of times.

For example say you want to display the term "hello world" ten times.

This is how you can do it:

for i in $(seq 10)
do
echo "hello world"
done
Change The Sequence Separator

By default, the seq command displays each number on a new line.

This can be changed to be any delimiting character that you wish to use.

For instance, if you wish to use a comma to separate the numbers use the following syntax:

seq -s , 10

If you would prefer to use a space then you need to put it in quotes:

seq -s " " 10
Make The Sequence Numbers The Same Length


When you output the numbers to a file you might be annoyed that as you step up through the tens and the hundreds that the numbers are of a different length.

For example:

    1
    2
    3
    10
    11
    99
    100
    200
    1000
    10000

You can make all the numbers the same length as follows:

seq -w 10000

When you run the above command the output will now be as follows:

    00001
    00002
    00003
    00010
    00011
    00099
    00100
    00200
    01000
    10000

Displaying Numbers In Reverse Order

You can display the numbers in a sequence in reverse order.

For instance, if you want to display the numbers 10 to 1 you can use the following syntax:

seq 10 -1 1
Floating Point Numbers

You can use the sequence command to work on floating point numbers as well.

For example, if you want to show every number between 0 and 1 with a 0.1 step you can do so as follows:

seq 0 0.1 1
Summary

The seq command is more useful when used as part of a bash script.

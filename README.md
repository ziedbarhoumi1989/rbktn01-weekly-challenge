Task

John is a worker, his job is to remove the screws from the machine.

A parameters screws will be given by a string, like this: "---+++", "-" and "+" are two type of screws.

John have two screwdrivers: slotted screwdriver and cross screwdriver. slotted screwdriver can remove screw "-", cross screwdriver can remove screw "+".

When John began to work, he stood in the first screw, with a screwdriver in his hand(He is always holding a screwdriver that can screw out the first one), another screwdriver in his tool kit.

Some actions and time consuming:

remove one screw :               1 second
move to adjacent screw position: 1 second
replace different screwdriver:   5 seconds

John has two modes of operation, for the example above "---+++", John will take the first mode:

From left to right, remove the screws, when the different 
types of screws appear, replace his screwdriver and continue.

In other cases, such as "-+-+-+", John will take second modes:

Remove the first type screws from left to right, then replace the
screwdriver, from left to right, or from right to left, remove
second type screws (from which side to start, depending on
which side is closer to John).

Our task is to calculate the total time when he removed these screws. return the number of seconds that which is the shorter one of two modes.

Specific time calculation to see the following:
Example:

example1:
screws="---+++" 
In order to be more clear, we use ABCDEF to represent them, 
the number in brackets is the time(seconds)
use the mode1:
remove A(1)+move to B and remove B(2)+move to C and remove C(2)+
move to D(1)+replace screwdriver(5)+remove D(1)+
move to E and remove E(2)+move to F and remove F(2)
total times=16 seconds
use the mode2: 
same as mode 1, omit the process
so, sc("---+++")=16

example2:
screws="-+-+-+"  (ABCDEF)
use the mode1:
remove A(1)+
move to B(1)+replace screwdriver(5)+remove B(1)+
move to C(1)+replace screwdriver(5)+remove C(1)+
move to D(1)+replace screwdriver(5)+remove D(1)+
move to E(1)+replace screwdriver(5)+remove E(1)+
move to F(1)+replace screwdriver(5)+remove F(1)
total times=36 seconds
in the mode 1,John replace the screwdriver 5 times, spent a lot of time.
use the mode2: 
remove A(1)+
move to B(1)+move to C and remove C(2)+
move to D(1)+move to E and remove E(2)+
move to F(1)+replace screwdriver(5)+remove F(1)+
move to E(1)+move to D and remove D(2)+
move to C(1)+move to B and remove B(2)
total time=20 seconds
the best time is 20 seconds,
so, sc("-+-+-+")=20

example3:
screws="-+-+-----------"
use mode 1:
total times=1+(1+5+1)+(1+5+1)+(1+5+1)+(1+5+1)
            +2+2+2+2+2+2+2+2+2+2=49 socends
use mode 2:
total times=1+1+2+1+2+2+2+2+2+2+2+2+2+2+2
            +11(John move from last '-' to the last '+')
            +5(replace screwdriver)+1+1+2=47 seconds
so, sc("-+-+-----------")=47

example4:
screws="-+-+-++++++++++"
use mode 1:
total times=1+(1+5+1)+(1+5+1)+(1+5+1)+(1+5+1)+(1+5+1)
            +2+2+2+2+2+2+2+2+2=54 socends
use mode 2:
total times=1+1+2+1+2
            +3(John move from last '-' to the first '+')
            +5(replace screwdriver)
            +1+1+2+1+2+2+2+2+2+2+2+2+2+2=40 seconds
so, sc("-+-+-++++++++++")=40
After finishing 'Learn Python the Hard Way' https://learnpythonthehardway.org/python3/, I was given an assignment to build an application as described below. Due to publishing restrictions, it cannot be made public, so currently just making the README available.

System Requirements:
--------------------
Python 2.7


Description:
------------

The goal was to create an application to find out certain information
for specific routes on a local commuter railroad which services a
number of towns in Kiwiland.

The details of the problem can be found in the 'problem.txt' file in the
application root directory.

Running the application:
------------------------
To use, run the following unix/linux command from the application root directory:
python journeys_info.py input.txt

The text file used for input must be stored in the application root directory.
The text file should follow the format as shown below, that is, the text followed
by a colon and then the data:

# The graph input should be <start><finish><distance>
GRAPH: AB5, BC4, CD8, DC8, DE6, AD5, CE2, EB3, AE7
# The distance of a specific route format is <start><next stop>...<finish>
Distance route1: ABC
Distance route2: AD
Distance route3: ADC
Distance route4: AEBCD
Distance route5: AED
# The number of trips with maximum stops format is <start>, <finish>, <max stops>
Route and max stops: C, C, 3
# Same format as above with max stops replaced by exact stops
Route and exact stops: A, C, 4
# The length of a shortest route format is <start>, <finish>
Shortest route1: A, C
Shortest route2: B, B
# Same as route max stops with distance in place of max stops
Number routes within distance: C, C, 30


Running the tests:
------------------
Input is tested using Unit Tests. To use, run the following unix/linux command from the application
root directory:
python -m unittest discover -v

Test Input:
For the test input, the towns are named using the first few letters of
the alphabet from A to D.  A route between two towns (A to B) with a
distance of 5 is represented as AB5.
Graph: AB5, BC4, CD8, DC8, DE6, AD5, CE2, EB3, AE7
Expected Output:
Output #1: 9
Output #2: 5
Output #3: 13
Output #4: 22
Output #5: NO SUCH ROUTE
Output #6: 2
Output #7: 3
Output #8: 9
Output #9: 9
Output #10: 7

Approach
--------
1. I started out by deciding how I would find all the possible paths that can be travelled.
   Trying to come up with an algorithm for this, I discovered I wasn't sure how I would deal
   with cycles in the route. I found a way around this by joining two paths (although not ideal). I went
   with the assumption that the routes did not repeat visits to towns.

2. I then decided on how I would structure the code into a class with the functions

3. The next step was to get some unit tests set up

4. I could see from the different required inputs, that repeat visits to towns would be inevitable.
   I wasn't sure how to go about finding all the possible routes which included these, as I wasn't
   too familiar with recursive functions. Eventually I found a way to do this, which works, but
   I know could be a lot neater.

5. Finally once all tests were passing, I worked on getting the application to run with the input
   data from a text file

This is just version one and needs refactoring.

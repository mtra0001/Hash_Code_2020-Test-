# More Pizza

Challenge can be found here - https://www.pietrolc.com/google-hash-code-more-pizza/

Simply the algorithm is about adding up the number of slices of the given Pizzas in reverse order. In latest updated version, after each completion repeats the same procedure with a skipping the elemnt before the lastly considered element of the input array. This way leads to approaches considering more different combinations for each problem and gives the perfect solution.

// Main loop is used to decrese the size of the currently considering range of input array

// Sub loop is used to find the solution using currently considering range of input array

main loop - - - - - - \            
|                      \
|  sub loop - - - \     |           
|  |               |    |
|   \ _ _ _ _ _ _ /     |
|                      /
 \ _ _ _ _ _ _ _ _ _  /
 
Lets take a look at the basic solution which is done inside the sub loop,

Example:

Input text

17 4

2 5 6 8

17 = the maximum number of Pizza slices to order

4 = the number of different types of Pizzas

Since there are 4 Pizzas the indexes of the pizzas are 0,1,2,3 respectively

An array traversal loop starts from end to the beginning and consider a one value at a time. Add it to the value of sum and compare

Initially,

Current Index	Sum	Solution

3	0	

Now the value of the sum variable is 0 and the index is 3

First take the last value(index is 3) and add it to the value of sum and compares with required number of slices(17 in this case)

0 + 8 = 8

Total is 8. But 8 < 17. Therefore,

Add current value to the sum variable
Note down the current index
Continue the procedure and move to the next value
Current Index	Sum	Solution

3	8	3

Add 6 and to the value of sum and compare

Current Index	Sum	Solution

2	8	3

8 + 6 = 14

Total is 14. But 14 < 17. Therefore,

Add current value to the sum variable
Note down the current index
Continue the procedure and move to the next value
Current Index	Sum	Solution

2	14	3, 2

Add 5 and to the value of sum and compare

Current Index	Sum	Solution

1	14	3, 2

14 + 5 = 19

Total is 19. But 19 > 17. Therefore,

DO NOT add current value to the sum variable
DO NOT note down the current index
Continue the procedure and move to the next value
Current Index	Sum	Solution

1	14	3, 2

Add 2 and to the value of sum and compare

Current Index	Sum	Solution

0	14	3, 2

14 + 2 = 16

Total is 16. But 16 < 17. Therefore,

Add current value to the sum variable
Note down the current index
Continue the procedure and move to the next value
Current Index	Sum	Solution

0	16	3, 2, 0

But there are no values remaining so the loop ends

By traversing through the Pizza list, the index numbers of the Pizzas that need to be order are 3, 2, 0.

So the output file should looks like,

3

3 2 0

The above solution was found with considering all the 4 input values from end to start without an initial solution. In order to move to next iteration last 2 values of the solution are subtracted from the sum, and the index of the element before the last element of solution is assigned as the starting index of the next iteration. So in the next iteration of the main loop considers about only 2 values (only 2 and 5) by skipping the last 2 vales (6 and 8). The procedure is same as the previous but the only difference is the number of values to consider.

Then it gives the solution

8 + 5 + 2 = 15

But this is not better than the previous solution which was 16. Therefore skip the last value once again and repeat the procedure again.

Likewise this procedure needs to be repeated until there is no values to be considered. Thereafter the solution with the highest score is taken as the best solution and will be written in to the output file.

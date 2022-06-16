# Decision-Graph-Automation
Code that uses kneedle algorithim, and various backend techniques to automate the detection of a gamma value within a L-Curve

The script kneedle.py is the full exploration of the reweighted gamma values from coefficients 0.1 to 0.9. To use this script, a user simply needs to type in the file path for the reweighted .dat files (Replacing the coefficeint with {j} and the exponent with {i} like: protein_name_{j}x10^{i}_work.dat) in the function filepath(), specifically where the filepath can be seen currently. In a similiar fashion, the user changes the desired protein name in the name function. This is used for graphs and output file naming.

The script stepwise starts with the minimum number of .dat files needed (in practice normally coefficients 0.1 to 0.6 or 0.7), and will then add one file at a time to the decision graph. Once the graph produces an identical gamma value consecutively 5 times, the code stops and the value is found. This was tested over multiple instances, and the 5-rep gamma theory held true for each analysis. In similiar fashion to the kneedle.py file, the user only needs to change the file name and file path at the top of the code.

The script lowrez.py starts with 6 intial points on the decission curve, 0.1, 0.4, 0.7, 1, 4, 7. From these points, the user runs the code and it will return 4 values to add to these coefficients. These values are determined by finding the gamma value, and then adding two points inbetween that value and the closest value to the left, and then does the same for the closet value on the right. Once the gamma is fully enclosed by +/- 2 on either end is when the user should stop as the value determined will be accurate. These values that the user needs to add will be output in the terminal with e^-1 being i=-1 and e^0 being i=0.

-VML

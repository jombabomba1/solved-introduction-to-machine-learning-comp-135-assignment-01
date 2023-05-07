Download Link: https://assignmentchef.com/product/solved-introduction-to-machine-learning-comp-135-assignment-01
<br>
This assignment will get you started using NumPy. If you are new to using that library (or Python in general), you probably want to start with the tutorial provided at:

<a href="https://numpy.org/devdocs/user/quickstart.html">https://numpy.org/devdocs/user/quickstart.html</a>

You have been supplied with some starter code, including the prototype for two functions that you need to complete. The code also contains detailed documentation of how the functions should operate, and some examples of their use. You can (and should) test your code to confirm that it does what is asked.

<ol>

 <li>(<em>5 pts.</em>) Along with your code, submit a completed version of the txt file.</li>

</ol>

An example has been provided, which you should edit appropriately to include:

<ul>

 <li>Your name.</li>

 <li>The time it took you to compete the assignment.</li>

 <li>Any resources you used to complete the assignment, including discussions with the instructor, TA’s, or fellow students, and any online or offline resources consulted. If you did not need to consult any outside resources, you can say so.</li>

 <li>A brief description of what parts, if any, of the assignment caused you to seek help.</li>

</ul>

<ol start="2">

 <li>(<em>10 pts.</em>) The first part of the code asks you to write a function to split data into a training set and a testing set (a very common task in ML). Your code will use basic NumPy array indexing and random number generation to take an input array containing <em>L </em>instances of <em>F</em>-dimensional data, and divide it into two mutually exclusive arrays of size <em>M </em>(for training) and <em>N </em>(for testing).</li>

</ol>

As part of its input, the function takes parameter frac_test, specifying the overall fraction of the data-set to use for testing purposes. It will use this fraction to determine the size <em>N</em>, <strong>rounding up </strong>to the nearest whole number: <em>N </em>= dfrac_test∗ <em>L</em>e

The function will also use NumPy functions like shuffle or permutation for doing random sampling of the data, so that the test/train instances are uniformly selected from the data-set:

<a href="https://docs.scipy.org/doc/numpy-1.15.1/reference/routines.random.html">https://docs.scipy.org/doc/numpy-1.15.1/reference/routines.random.html</a>

Furthermore, we want the results of the function to be <em>reproducible</em>, for scientific purposes. That means that there should be a way to specify a source of randomness (a <em>seed</em>) such that it is possible to duplicate any random selection. In NumPy, this is generally handled by using a RandomState instance, or via an integer seed. See the linked discussion from the source code comments for insight into using such seeds in your code.

<strong>Notes</strong>: read the documentation of the function supplied with the starter code carefully. Ensure that your code meets the requirements as given. In addition, be sure that your code uses <em>only </em>basic Python and functions from NumPy. <em>Do not </em>call functions for data-set generation and manipulation from libraries like sklearn.

<ol start="3">

 <li>(<em>10 pts.</em>) The other function you are to complete finds <em>nearest neighbors </em>of given datainstances. That is, given a set of <em>F</em>-dimensional data of size <em>N</em>, and <em>Q </em>query instances (also <em>F</em>-dimensional), we want to compute the <em>K </em>closest vectors found in the data, for some integer value <em>K</em>, and for each query instance (for a total of <em>Q </em>× <em>K </em>neighbors).</li>

</ol>

In computing “closeness,” we will use the <em>Euclidean distance </em>between vectors. For two vectors

<ol>

 <li><strong>x</strong>) and <strong>x</strong>), this distance is given by:</li>

</ol>

Your function will take in a data-set (a 2-dimensional array of size <em>N </em>× <em>F</em>) and a query-set (a 2-dimensional array of size <em>Q</em>×<em>F</em>), and return a 3-dimensional array (of size <em>Q</em>×<em>K </em>×<em>F</em>), where each row (indexed by <em>Q</em>) consists of the <em>K </em>nearest neighbors of the corresponding query vector. These neighbors should appear <em>in order</em>, closest to least-close.

<strong>Notes</strong>: it is possible that there will be ties among neighbors. If this occurs, such ties can be broken however you like (randomly or not). Again, be sure that your code uses <em>only </em>basic Python and functions from NumPy. <em>Do not </em>call functions from libraries like sklearn.

<strong>Submission details</strong>: Your work should satisfy the following requirements:

<ul>

 <li>Your code must work properly with the versions of Python and other libraries that are part of the COMP 135 standard environment. The class website contains instructions for installing and using this environment.</li>

</ul>

<a href="http://www.cs.tufts.edu/comp/135/resources/">http://www.cs.tufts.edu/comp/135/resources/</a>

You can write the Python code using whatever tools you like, but you should ensure that the code executes properly. (See next page for an example of how you might test your code.)

<ul>

 <li>When you submit your code, only submit the completed functions. Your own testing code should be commented out or otherwise removed.</li>

 <li>All materials for this assignment should be submitted as part of a single ZIP archive.</li>

 <li>After submission, the Gradescope site will run an auto-grader utility and give you a numerical score. If there are errors in any tests, these will be indicated. It is recommended that you submit your work well before the deadline in order to help you determine if there are bugs or missing components that need to be corrected.</li>

</ul>

<strong>Testing your code</strong>: There are a variety of ways of testing your code. Here, we describe one. You may want to test your code in some other way; this is fine, but you should test it in some way.

<ul>

 <li>Start by activating the COMP 135 environment, from the directory containing your py file. Once the environment is active, you can load your file into the Python interactive shell (doing this makes the functions written in that file available from the shell):</li>

</ul>

$python -i hw1.py

<ul>

 <li>After you have loaded it, you can call functions from your file (and from NumPy, since py starts by importing that library as np). For instance, you can run the first few lines of testing code described in the documentation for the first function as follows, to generate an identity matrix of size (10 × 10), and then split it into a (3 × 10) testing set and a (7 × 10) training set:</li>

</ul>

&gt;&gt;&gt; x_LF = np.eye(10)

&gt;&gt;&gt; train_MF, test_NF = split_into_train_and_test(x_LF, frac_test=0.3,

random_state=np.random.RandomState(0))

<ul>

 <li>The rest of the testing code can also be run in this fashion, to test the correct behavior of the function. Similar tests can be run on the second function you wrote as well.</li>

 <li>Again, the code you submit should only contain the two functions asked for (and any supporting functions you write to implement them). Your submission <em>should not </em>include any testing code itself. .</li>

</ul>
Download Link: https://assignmentchef.com/product/solved-fys-stk3155-project-3-defining-the-data-sets-to-analyze-yourself
<br>
<h2></h2>

For project 3, you can propose own data sets that relate to your research interests or just use existing data sets from say

<ol>

 <li><a href="https://www.kaggle.com/datasets">Kaggle</a></li>

 <li>The <a href="https://archive.ics.uci.edu/ml/datasets.html">University of California at Irvine (UCI) with its machine learning </a><a href="https://archive.ics.uci.edu/ml/datasets.html">repository</a></li>

</ol>

The approach to the analysis of these new data sets should follow to a large extent what you did in projects 1 and 2. That is:

<ol>

 <li>Whether you end up with a regression or a classification problem, you should employ at least two of the methods we have discussed among <strong>linear regression (including Ridge and Lasso)</strong>, <strong>Logistic Regression</strong>, <strong>Neural Networks</strong>, <strong>Support Vector Machines </strong>and <strong>Decision Trees, Random Forests</strong>, <strong>Bagging and Boosting</strong>. You could for example explore all of the approaches from decision trees, via bagging and voting classifiers, to random forests, boosting and finally XGboost. If you wish to venture into <strong>convolutional neural networks </strong>or <strong>recurrent neural networks</strong>, or extensions of neural networkds, feel free to do so.</li>

 <li>For project 3, you should feel free to use your own codes from projects 1 and 2, eventually write your own for SVMs and/or Decision trees/random forests/bagging/boosting’ or use the available functionality of <strong>ScikitLearn</strong>, <strong>Tensorflow</strong>, etc.</li>

 <li>The estimates you used and tested in projects 1 and 2 should also be included, that is the <em>R</em>2-score, <strong>MSE</strong>, confusion matrix, accuracy score, information gain, cross-validation and/or bootstrap if these are relevant.</li>

</ol>

<em> </em>c 1999-2019, “Data Analysis and Machine Learning

FYS-STK3155/FYS4155″:”http://www.uio.no/studier/emner/matnat/fys/FYS3155/index-

eng.html”. Released under CC Attribution-NonCommercial 4.0

license

<ol start="4">

 <li>If possible, you should link the data sets with exisiting research and analyses thereof. Scientific articles which have used Machine Learning algorithms to analyze the data are highly welcome. Perhaps you can improve previous analyses and even publish a new article?</li>

 <li>A critical assessment of the methods with ditto perspectives and recommendations is also something you need to include.</li>

</ol>

All in all, the report should follow the same pattern as the two previous ones, with abstract, introduction, methods, code, results, conclusions etc..

We propose also an alternative to the above. This is a project on using machine learning methods (neural networks mainly) to the solution of ordinary differential equations and partial differential equations, with a final twist on how to diagonalize a symmetric matrix with neural networks..

This is a field with a large interest recently, spanning from studies of turbulence in fluid mechanics and meteorology to the solution of quantum mechanical systems.

<h2>The basic structure of your project</h2>

Here follows a set up on how to structure your report and analyze the data you have opted for.

<strong>Part a). </strong>The first part deals with structuring and reading the data, much along the same lines as done in projects 1 and 2. Explain how the data are produced and place them in a proper context.

<strong>Part b). </strong>You need to include at least two central algorithms, or as an alternative explore methods from decisions tree to bagging, random forests and boosting. Explain the basics of the methods you have chosen to work with. This would be your theory part.

<strong>Part c).   </strong>Then describe your algorithm and its implementation and tests you have performed.

<strong>Part d). </strong>Then presents your results and findings, link with existing literature and more.

<strong>Part e).  </strong>Finally, here you should present a critical assessment of the methods you have studied and link your results with the existing literature.

<h2>Solving partial differential equations with neural networks</h2>

For this variant of project 3, we will assume that you have some background in the solution of partial differential equations using finite difference schemes.

We will study the solution of the diffusion equation in one dimension using a standard explicit scheme and neural networks to solve the same equations.

For the explicit scheme, you can study for example chapter 10 of the lecture notes in <a href="https://github.com/CompPhysics/ComputationalPhysics/blob/master/doc/Lectures/lectures2015.pdf">Computational Physics</a> or alternative sources. For the solution of ordinary and partial differential equations using neural networks, the lectures by <a href="https://compphysics.github.io/MachineLearning/doc/pub/odenn/html/odenn-bs.html">Kristine Baluka Hein</a> at this course are highly recommended.

For the machine learning part you can use your own code from project 2 or the functionality of for example <strong>Tensorflow/Keras</strong>.

<strong>Part a), setting up the problem. </strong>The physical problem can be that of the temperature gradient in a rod of length <em>L </em>= 1 at <em>x </em>= 0 and <em>x </em>= 1. We are looking at a one-dimensional problem

<em>,t &gt; </em>0<em>,x ∈ </em>[0<em>,L</em>]

or

<em>u</em><em>xx </em>= <em>u</em><em>t,</em>

with initial conditions, i.e., the conditions at <em>t </em>= 0,

<em>u</em>(<em>x,</em>0) = sin(<em>πx</em>)            0 <em>&lt; x &lt; L,</em>

with <em>L </em>= 1 the length of the <em>x</em>-region of interest. The boundary conditions are

<em>u</em>(0<em>,t</em>) = 0         <em>t ≥ </em>0<em>,</em>

and

<em>u</em>(<em>L,t</em>) = 0          <em>t ≥ </em>0<em>.</em>

The function <em>u</em>(<em>x,t</em>) can be the temperature gradient of a rod. As time increases, the velocity approaches a linear variation with <em>x</em>.

We will limit ourselves to the so-called explicit forward Euler algorithm with discretized versions of time given by a forward formula and a centered difference in space resulting in

<em><sub>ut </sub></em><em><sub>≈ </sub>u</em>(<em>x,t </em>+ ∆<em>t</em>) <em>− u</em>(<em>x,t</em>) <sub>= </sub><em>u</em>(<em>x</em><em>i,t</em><em>j </em>+ ∆<em>t</em>) <em>− u</em>(<em>x</em><em>i,t</em><em>j</em>)

∆<em>t                                               </em>∆<em>t</em>

and

<em>u</em>(<em>x </em>+ ∆<em>x,t</em>) <em>− </em>2<em>u</em>(<em>x,t</em>) + <em>u</em>(<em>x − </em>∆<em>x,t</em>) <em>u</em><em>xx</em><em>,</em>

or

<em>u</em>(<em>x<sub>i </sub></em>+ ∆<em>x,t<sub>j</sub></em>) <em>− </em>2<em>u</em>(<em>x<sub>i</sub>,t<sub>j</sub></em>) + <em>u</em>(<em>x<sub>i </sub>− </em>∆<em>x,t<sub>j</sub></em>) <em>u</em><em>xx</em><em>.</em>

Write down the algorithm and the equations you need to implement. Find also the analytical solution to the problem.

<strong>Part b).  </strong>Implement the explicit scheme algorithm and perform tests of the solution for ∆<em>x </em>= 1<em>/</em>10, ∆<em>x </em>= 1<em>/</em>100 using ∆<em>t </em>as dictated by the stability limit of the explicit scheme. The stability criterion for the explicit scheme requires that ∆<em>t/</em>∆<em>x</em><sup>2 </sup><em>≤ </em>1<em>/</em>2.

Study the solutions at two time points <em>t</em><sub>1 </sub>and <em>t</em><sub>2 </sub>where <em>u</em>(<em>x,t</em><sub>1</sub>) is smooth but still significantly curved and <em>u</em>(<em>x,t</em><sub>2</sub>) is almost linear, close to the stationary state.

<strong>Part c) Neural networks. </strong>Study now the lecture notes on solving ODEs and PDEs with neural network and use either your own code from project 2 or the functionality of tensorflow/keras to solve the same equation as in part

b). Discuss your results and compare them with the standard explicit scheme. Include also the analytical solution and compare with that.

<strong>Part d) Solving eigenvalue problems. </strong>Follow the discussion in the work of Yi <em>et al. </em>in the article from <a href="https://www.sciencedirect.com/science/article/pii/S0898122104901101">Computers and Mathematics with Applications </a><a href="https://www.sciencedirect.com/science/article/pii/S0898122104901101">47, 1155 (2004)</a><a href="https://www.sciencedirect.com/science/article/pii/S0898122104901101">,</a> and use your differential equation solver with neural networks, set up a simple square, real and symmetric 6 <em>× </em>6 matrix and find the eigenvalues. Compare with the solution from numerical diagonalization with standard eigenvalue solvers from linear algebra.

<strong>Part e). </strong>Finally, present a critical assessment of the methods you have studied and discuss the potential for the solving differential equations and eigenvalue problems with machine learning methods.

<h2>Introduction to numerical projects</h2>

Here follows a brief recipe and recommendation on how to write a report for each project.

<ul>

 <li>Give a short description of the nature of the problem and the eventual numerical methods you have used.</li>

 <li>Describe the algorithm you have used and/or developed. Here you may find it convenient to use pseudocoding. In many cases you can describe the algorithm in the program itself.</li>

 <li>Include the source code of your program. Comment your program properly.</li>

 <li>If possible, try to find analytic solutions, or known limits in order to test your program when developing the code.</li>

 <li>Include your results either in figure form or in a table. Remember to label your results. All tables and figures should have relevant captions and labels on the axes.</li>

 <li>Try to evaluate the reliabilty and numerical stability/precision of your results. If possible, include a qualitative and/or quantitative discussion of the numerical stability, eventual loss of precision etc.</li>

 <li>Try to give an interpretation of you results in your answers to the problems.</li>

 <li>Critique: if possible include your comments and reflections about the exercise, whether you felt you learnt something, ideas for improvements and other thoughts you’ve made when solving the exercise. We wish to keep this course at the interactive level and your comments can help us improve it.</li>

 <li>Try to establish a practice where you log your work at the computerlab. You may find such a logbook very handy at later stages in your work, especially when you don’t properly remember what a previous test version of your program did. Here you could also record the time spent on solving the exercise, various algorithms you may have tested or other topics which you feel worthy of mentioning.</li>

</ul>

<h2>Format for electronic delivery of report and programs</h2>

The preferred format for the report is a PDF file. You can also use DOC or postscript formats or as an ipython notebook file. As programming language we prefer that you choose between C/C++, Fortran2008 or Python. The following prescription should be followed when preparing the report:

<ul>

 <li>Use Devilry to hand in your projects, log in at <a href="http://devilry.ifi.uio.no/">http://devilry.ifi. </a><a href="http://devilry.ifi.uio.no/">no</a> with your normal UiO username and password and choose either ’fysstk3155’ or ’fysstk4155’. There you can load up the files within the deadline.</li>

 <li>Upload <strong>only </strong>the report file! For the source code file(s) you have developed please provide us with your link to your github domain. The report file should include all of your discussions and a list of the codes you have developed. Do not include library files which are available at the course homepage, unless you have made specific changes to them.</li>

 <li>In your git repository, please include a folder which contains selected results. These can be in the form of output from your code for a selected set of runs and input parameters.</li>

 <li>In this and all later projects, you should include tests (for example unit tests) of your code(s).</li>

 <li>Comments from us on your projects, approval or not, corrections to be made etc can be found under your Devilry domain and are only visible to you and the teachers of the course.</li>

</ul>

Finally, we encourage you to collaborate. Optimal working groups consist of 2-3 students. You can then hand in a common report.

<h2>Software and needed installations</h2>

If you have Python installed (we recommend Python3) and you feel pretty familiar with installing different packages, we recommend that you install the following Python packages via <strong>pip </strong>as

<ol>

 <li>pip install numpy scipy matplotlib ipython scikit-learn tensorflow sympy pandas pillow</li>

</ol>

For Python3, replace <strong>pip </strong>with <strong>pip3</strong>.

See below for a discussion of <strong>tensorflow </strong>and <strong>scikit-learn</strong>.

For OSX users we recommend also, after having installed Xcode, to install <strong>brew</strong>. Brew allows for a seamless installation of additional software via for example

<ol>

 <li>brew install python3</li>

</ol>

For Linux users, with its variety of distributions like for example the widely popular Ubuntu distribution you can use <strong>pip </strong>as well and simply install Python as

<ol>

 <li>sudo apt-get install python3 (or python for python2.7)</li>

</ol>

etc etc.

If you don’t want to install various Python packages with their dependencies separately, we recommend two widely used distrubutions which set up all relevant dependencies for Python, namely

<ol>

 <li><a href="https://docs.anaconda.com/">Anaconda</a> Anaconda is an open source distribution of the Python and R programming languages for large-scale data processing, predictive analytics, and scientific computing, that aims to simplify package management and deployment. Package versions are managed by the package management system <strong>conda</strong></li>

 <li><a href="https://www.enthought.com/product/canopy/">Enthought canopy</a> is a Python distribution for scientific and analytic computing distribution and analysis environment, available for free and under a commercial license.</li>

</ol>

Popular software packages written in Python for ML are

<ul>

 <li><a href="http://scikit-learn.org/stable/">Scikit-learn</a><a href="http://scikit-learn.org/stable/">,</a></li>

 <li><a href="https://www.tensorflow.org/">Tensorflow</a><a href="https://www.tensorflow.org/">, </a> <a href="http://pytorch.org/">PyTorch</a> and</li>

 <li><a href="https://keras.io/">Keras</a><a href="https://keras.io/">.</a></li>

</ul>

These are all freely available at their respective GitHub sites. They encompass communities of developers in the thousands or more. And the number of code developers and contributors keeps increasin
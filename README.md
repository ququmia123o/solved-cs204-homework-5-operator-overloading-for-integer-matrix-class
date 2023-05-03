Download Link: https://assignmentchef.com/product/solved-cs204-homework-5-operator-overloading-for-integer-matrix-class
<br>
<h2>Introduction</h2>

<strong> </strong>In this homework, you are asked to implement a class for <em>integer matrices </em>and overload some operators. The details of these operators and the functions that you will implement are given below. Our focus in this homework is on the class design and implementation. The usage of this class in the main program will be given to you.




<h2>Matrix Class Design</h2>

<strong> </strong>

You have to keep the <em>rowNumber,</em> <em>columnNumber </em>and<em> elements </em>of the matrix as <u>private</u> data members of the class. Elements of the matrix must be stored in a <strong>dynamic matrix of integers</strong> with <em>rowNumber</em> rows and <em>columnNumber</em> elements per row. Since the matrix is dynamic one, as <em>elements</em>, you will need to use a <u>pointer to pointer</u>. Dynamic matrices were covered in week 4 of the course. Please refer to lecture notes to recall.




Your class implementation must include the following basic class functions:

<ul>

 <li><u>Default constructor:</u> creates a <em>Matrix </em>object with zero rows and zero columns This constructor does not allocate memory for the elements of the matrix.</li>

 <li><u>Constructor with <em>rowNum, columnNum, init </em>parameters:</u> creates a <em>Matrix </em>object with <em>rowNum</em> rows and <em>columnNum</em> columns, and allocates enough memory. Initial values of all of the elements must be set to <em>init</em>. Please refer to week 4 material about creating a dynamic matrix via pointers. If <em>rowNum</em> and/or <em>columnNum</em> is/are non-positive, then an empty matrix with zero rows and zero columns must be created.</li>

 <li><u>Deep copy constructor:</u> takes a <em>Matrix </em>object as const-reference parameter and creates a new <em>Matrix </em>object as the deep copy of the parameter.</li>

 <li><u>Destructor:</u> By definition, destructor deletes all dynamically allocated memory of the object and returns them to the heap.</li>

</ul>




In this homework, you will overload several operators for the <em>Matrix</em> class. These operators and the details of overloading are given below. You can overload operators as member or free functions.






















+ This operator will be overloaded such that it calculates and returns the summation of two <em>Matrix </em>operands. The mathematical definition of + operation on matrices <strong> </strong>and <strong> </strong>is given below. Here assume that the dimensions of the operands are the same; you do not need to check the dimension equality in the operator implementation.







<strong> </strong>

– This operator will be overloaded such that it calculates and returns the difference of two <em>Matrix </em>operands. The mathematical definition of – operation on matrixes <strong> </strong>and <strong> </strong>is given below. Here assume that the dimensions of the operands are the same; you do not need to check the dimension equality in the operator implementation.

<strong> </strong>

<table width="666">

 <tbody>

  <tr>

   <td width="57"> </td>

   <td width="609"> </td>

  </tr>

  <tr>

   <td width="57">= </td>

   <td width="609">This operator will be overloaded such that it will assign the <em>Matrix</em> object on the right handside of the operator to the <em>Matrix</em> object on the left hand-side. This function must be implemented in a way to allow cascaded assignments. Due to C++ language rules, this operator must be a member function (cannot be free function).</td>

  </tr>

  <tr>

   <td width="57">==</td>

   <td width="609">This operator will be overloaded such that it will check two <em>Matrix</em> objects for equality. If the sizes of these two matrices are not the same, then this operator directly returns false. If the sizes are the same, then all of the corresponding elements of the matrices must be the same in order</td>

  </tr>

 </tbody>

</table>

to return true. Otherwise, the operator returns false.<strong> </strong>




! This operator will be overloaded such that it will return the transpose of the matrix operand. In linear algebra, the transpose of a matrix is an operator which switches the rows with columns.

Note that this is a unary operator (i.e. it takes a single operand). That means, if you implement it as a member function, the function does not take any parameters and processes the object on which the operator function is called. Alternatively, you can implement it as a free function; in this case, the function takes only one const-reference <em>Matrix</em> parameter and processes it. In either case, the transposed value must be returned from the function <u>as value</u> (i.e. <u>not</u> reference) and you will <u>not</u> change the content of its operand.




The mathematical definition of transpose is given below.













Other than these operators, you will need to implement the following accessors (getters) and mutator (setter) as member functions.




<table width="665">

 <tbody>

  <tr>

   <td width="189">getRowNumber</td>

   <td width="477">returns the number of rows of the <em>Matrix</em> object. No parameters.</td>

  </tr>

  <tr>

   <td width="189">getColumnNumber</td>

   <td width="477">returns the number of columns of the <em>Matrix</em> object. No parameters.</td>

  </tr>

  <tr>

   <td width="189">getElementAt</td>

   <td width="477">takes row and column indices as parameters and returns the matrix element at this position</td>

  </tr>

  <tr>

   <td width="189">setElementAt</td>

   <td width="477">takes row and column indices, and an integer value as parameters. The function does not return anything but assigns the parameter value to the corresponding matrix element.</td>

  </tr>

 </tbody>

</table>




You also need to write member function named print that does not take any parameters, does not return anything, but displays the content of the matrix.




<strong>A life-saving advice: </strong>The getters above need to be <strong>const member functions</strong> so that they work fine with const-reference parameters. If you do not remember what “const member function” is, please refer to CS201 notes or simply Google it!




In order the see the usage and the effects of these operators, please see <strong>sample runs</strong> and the provided <strong>main.cpp</strong>.




In this homework, you are allowed to implement some other helper member functions, accessors and mutators, if needed. However, you are <strong><u>not allowed to use friend functions and friend classes</u></strong>.




<strong>You have to have separate header and implementation files, in addition to the main.cpp.  </strong>

<strong> </strong>

<strong>Please do not make use any standard or non-standard <em>container </em>or<em> matrix </em>classes in your homework; <u>you will implement your own class from scratch.</u>  </strong>













<h2>main.cpp</h2>

In this homework, <strong>main.cpp </strong>file is given to you within this homework package and we will test your codes with this main function with different inputs. <u>You are not allowed to make any modifications</u> <u>in the main function (of course, you can edit the file to add </u><u>#includes, etc. to the beginning of the</u> <u>file).</u> Inputs are explained with appropriate prompts so that you do not get confused. We strongly recommend you to examine main.cpp file and sample runs before starting your homework.




<h2>Sample Runs</h2>




Some sample runs are given below, but these are not comprehensive, therefore you have to consider <strong>all possible cases</strong> to get full mark. Especially try different matrix values (other than the ones given in the sample runs) and extreme cases.

<strong> </strong>

<strong>Sample Run 1: </strong>

<strong> </strong>

Please enter the row number of Matrix m1:

<h1>2</h1>

Please enter the column number of Matrix m1:

<h1>3</h1>

Please enter the init value of Matrix m1:

<strong>1 </strong>




Matrix m1:

<ul>

 <li>2 3</li>

 <li>3 4</li>

</ul>




Please enter the row number of Matrix m2:

<strong>2 </strong>

Please enter the column number of Matrix m2:

<h1>3</h1>

Please enter the init value of Matrix m2: <strong>1 </strong>




<h1>Matrix m2:</h1>

<ul>

 <li>2 3</li>

 <li>3 4</li>

</ul>




Please enter the row number of Matrix m3:

<h1>3</h1>

Please enter the column number of Matrix m3:

<h1>3</h1>

Please enter the init value of Matrix m3: <strong>1 </strong>




<h1>Matrix m3:</h1>

<ul>

 <li>2 3</li>

 <li>3 4</li>

 <li>4 5</li>

</ul>




Matrix m4:

<ul>

 <li>2 3</li>

 <li>3 4</li>

 <li>4 5</li>

</ul>




m1 is equal to m2.

m3 = m1 + m2 + m1:

3 6 9

6 9 12  m4 = m2 – m1 – m2:

<ul>

 <li>-2 -3</li>

 <li>-3 -4</li>

</ul>




Transpose of m3:

3 6

6 9

9 12




Assigning m4 = m2 = m3.

Matrix m4:

3 6

6 9

9 12




Matrix m2:

3 6

6 9

9 12




Matrix m3:

3 6

6 9

9 12 <strong> </strong>

<strong> </strong>

<strong> </strong>

<strong>Sample Run 2: </strong>

Please enter the row number of Matrix m1:

<strong>2 </strong>

Please enter the column number of Matrix m1:

<strong>5 </strong>

Please enter the init value of Matrix m1:

<strong>1 </strong>




Matrix m1: 1 2 3 4 5

2 3 4 5 6




Please enter the row number of Matrix m2:

<strong>2 </strong>

Please enter the column number of Matrix m2:

<strong>2 </strong>

Please enter the init value of Matrix m2:

<strong>2 </strong>




Matrix m2: 2 4

4 6




Please enter the row number of Matrix m3:

<strong>1 </strong>

Please enter the column number of Matrix m3:

<strong>1 </strong>

Please enter the init value of Matrix m3: <strong>1 </strong>




Matrix m3:

1




Matrix m4:

1

m1 is not equal to m2.

m3 = m1 + m2 + m1:

Matrix m1 and m2 do not have the same dimensions. Cannot be added.

m4 = m2 – m1 – m2:

Matrix m1 and m2 do not have the same dimensions. Cannot be subtracted.




Transpose of m3:

1




Assigning m4 = m2 = m3.

Matrix m4:

1




Matrix m2:

1




Matrix m3:

1







<strong>Sample Run 3: </strong>




Please enter the row number of Matrix m1:

<strong>-1 </strong>

Please enter the column number of Matrix m1:

<strong>2 </strong>

Please enter the init value of Matrix m1: <strong>1 </strong>




Matrix m1:




Please enter the row number of Matrix m2:

<strong>0 </strong>

Please enter the column number of Matrix m2:

<strong>0 </strong>

Please enter the init value of Matrix m2: <strong>3 </strong>




Matrix m2:




Please enter the row number of Matrix m3:

<strong>2 </strong>

Please enter the column number of Matrix m3:

<strong>2 </strong>

Please enter the init value of Matrix m3: <strong>1 </strong>




Matrix m3:

<ul>

 <li>2</li>

 <li>3</li>

</ul>




Matrix m4:

<ul>

 <li>2</li>

 <li>3</li>

</ul>

m1 is equal to m2.

m3 = m1 + m2 + m1:

m4 = m2 – m1 – m2:




Transpose of m3:




Assigning m4 = m2 = m3.

Matrix m4:




Matrix m2:  Matrix m3:




<strong> </strong>

<strong> </strong>

<h2>Some Important Rules</h2>

You should prepare (or at least test) your program using MS Visual Studio 2012 C++. We will use the standard C++ compiler and libraries of the abovementioned platform while testing your homework. It’d be a good idea to write your name and last name in the program (as a comment line of course).

<strong> </strong>

Submissions guidelines are below. Some parts of the grading process are automatic. Students are expected to strictly follow these guidelines in order to have a smooth grading process. If you do not follow these guidelines, depending on the severity of the problem created during the grading process, 5 or more penalty points are to be deducted from the grade. Name your solution, project, cpp file that contains your main program using the following convention (the necessary file extensions such as .sln, .cpp, etc, are to be added to it):




“SUCourseUserName_YourLastname_YourName_HWnumber”




Your SUCourse user name is actually your SUNet user name which is used for checking sabanciuniv emails. Do NOT use any spaces, non-ASCII and Turkish characters in the file name. For example, if your SUCourse user name is cago, name is Çağlayan, and last name is Özbugsızkodyazaroğlu, then the file name must be:




Cago_Ozbugsizkodyazaroglu_Caglayan_hw5

<strong> </strong>

In some homework assignments, you may need to have more than one .cpp or .h files to submit. In this case add informative phrases after the hw number. However, do not add any other character or phrase to the file names.




Now let us explain which files will be included in the submitted package. Visual Studio 2012 will create two <em>debug </em>folders, one for the solution and the other one for the project. You should delete these two <em>debug </em>folders. Moreover, if you have run your program in release mode, Visual Studio may create <em>release </em>folders; you should delete these as well. Apart from these, Visual Studio 2012 creates a file extension of <em>.sdf</em>; you will also delete this file. The remaining content of your solution folder is to be submitted after compression. Compress your solution and project folders using WINZIP or WINRAR programs. Please use “zip” compression. “rar” or another compression mechanism is NOT allowed. Our homework processing system works only with zip files. Therefore, make sure that the resulting compressed file has a zip extension. Check that your compressed file opens up correctly and it contains all of the solution, project and source code files that belong to the latest version of your homework. Especially double-check that the zip file contains your cpp and (if any) header files that you wrote for the homework.

<strong> </strong>

Moreover, we strongly recommend you to check whether your zip file will open up and run correctly. To do so, unzip your zip file to another location. Then, open your solution by clicking the file that has a file extension of .sln. Clean, build and run the solution; if there is no problem, you could submit your zip file. Please note that the deleted files/folders may be regenerated after you build and run your program; this is normal, but do not include them in the submitted zip file.




You will receive no credits if your compressed zip file does not expand or it does not contain the correct files. The naming convention of the zip file is the same. The name of the zip file should be as follows:




SUCourseUserName_YourLastname_YourName_HWnumber.zip




For example, zubzipler_Zipleroglu_Zubeyir_hw5.zip is a valid name, but




Hw4_hoz_HasanOz.zip, HasanOzHoz.zip




are <strong>NOT </strong>valid names.

<strong> </strong>

<strong>Submit via SUCourse ONLY! </strong>You will receive no credits if you submit by other means (e-mail, paper, etc.).

Successful submission is one of the requirements of the homework. If, for some reason, you cannot successfully submit your homework and we cannot grade it, your grade will be 0.

Good Luck!

Taha Atahan Akyıldız, Albert Levi
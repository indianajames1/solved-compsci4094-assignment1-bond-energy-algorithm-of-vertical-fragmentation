Download Link: https://assignmentchef.com/product/solved-compsci4094-assignment1-bond-energy-algorithm-of-vertical-fragmentation
<br>
In this assignment you are required to implement the Bond Energy Algorithm of vertical fragmentation. Your code should contains two separate procedures AA Generator and CA Generator, where AA Generator takes the input of all attributes of a relation, a set of queries and their access frequencies at different sites, and produces the output of an affinity matrix AA, and CA Generator takes input of an affinity matrix AA and produces a clustered affinity matrix CA. For description of the BEA algorithm, definitions of AA and CA, please see lecture slides/textbook.

In this assignment, the Attribute Affinity is measured by the extended Otsuka-Ochiai coefficient (https://en.wikipedia.org/wiki/Yanosuke Otsuka) instead of the traditional method described in the textbook. The following equations show the details of the computation, where n is the number of attributes, and m is the number of sites, <em>A<sub>ik </sub></em>is the number of times Attribute <em>A<sub>i </sub></em>is accessed by Query <em>q<sub>k</sub></em>, considering of all sites. For the result of division, you must round it up to the nearest integer.

<em>,</em>

<table width="109">

 <tbody>

  <tr>

   <td width="31"> </td>

   <td width="31">S1</td>

   <td width="31">S2</td>

   <td width="15">S3</td>

  </tr>

  <tr>

   <td width="31">q1</td>

   <td width="31">15</td>

   <td width="31">20</td>

   <td width="15">10</td>

  </tr>

  <tr>

   <td width="31">q2</td>

   <td width="31">5</td>

   <td width="31">0</td>

   <td width="15">0</td>

  </tr>

  <tr>

   <td width="31">q3</td>

   <td width="31">25</td>

   <td width="31">25</td>

   <td width="15">25</td>

  </tr>

  <tr>

   <td width="31">q4</td>

   <td width="31">5</td>

   <td width="31">0</td>

   <td width="15">0</td>

  </tr>

 </tbody>

</table>

<h1>Example</h1>

<strong>For AA Generator:</strong>

<strong>Input</strong>

<ul>

 <li>The relation, called PROJ, has the following features <em>A<sub>i</sub></em>:</li>

</ul>

<h2>Label     Name A1             PNO A2                PNAME</h2>

A3         BUDGET A4              LOC

<ul>

 <li>Queries (qi):</li>

</ul>

q1: SELECT BUDGET FROM PROJ WHERE PNO=Value q2: SELECT PNAME, BUDGET FROM PROJ q3: SELECT PNAME FROM PROJ WHERE LOC=Value q4: SELECT SUM(BUDGET) FROM PROJ WHERE LOC=Value

<ul>

 <li>Access frequency matrix ACC, where Si denotes the i-th site:</li>

</ul>

<strong>Output</strong>

<ul>

 <li>The attribute affinity matrix AA:</li>

</ul>

<table width="380">

 <tbody>

  <tr>

   <td width="293">A1</td>

   <td width="34">A2</td>

   <td width="34">A3</td>

   <td width="18">A4</td>

  </tr>

  <tr>

   <td width="293">                                                                           A1     45</td>

   <td width="34">0</td>

   <td width="34">41</td>

   <td width="18">0</td>

  </tr>

  <tr>

   <td width="293">                                                                           A2     0</td>

   <td width="34">71</td>

   <td width="34">1</td>

   <td width="18">71</td>

  </tr>

  <tr>

   <td width="293">                                                                           A3     41</td>

   <td width="34">1</td>

   <td width="34">38</td>

   <td width="18">1</td>

  </tr>

  <tr>

   <td width="293">                                                                           A4     0<strong>For CA Generator:</strong><strong>Input</strong>• The attribute affinity matrix AA:</td>

   <td width="34">71</td>

   <td width="34">1</td>

   <td width="18">71</td>

  </tr>

  <tr>

   <td width="293">A1</td>

   <td width="34">A2</td>

   <td width="34">A3</td>

   <td width="18">A4</td>

  </tr>

  <tr>

   <td width="293">                                                                           A1     45</td>

   <td width="34">0</td>

   <td width="34">41</td>

   <td width="18">0</td>

  </tr>

  <tr>

   <td width="293">                                                                           A2     0</td>

   <td width="34">71</td>

   <td width="34">1</td>

   <td width="18">71</td>

  </tr>

  <tr>

   <td width="293">                                                                           A3     41</td>

   <td width="34">1</td>

   <td width="34">38</td>

   <td width="18">1</td>

  </tr>

  <tr>

   <td width="293">                                                                           A4     0<strong>Output</strong>• The attribute affinity matrix CA:</td>

   <td width="34">71</td>

   <td width="34">1</td>

   <td width="18">71</td>

  </tr>

  <tr>

   <td width="293">A1</td>

   <td width="34">A3</td>

   <td width="34">A4</td>

   <td width="18">A2</td>

  </tr>

  <tr>

   <td width="293">                                                                           A1     45</td>

   <td width="34">41</td>

   <td width="34">0</td>

   <td width="18">0</td>

  </tr>

  <tr>

   <td width="293">                                                                           A3     41</td>

   <td width="34">38</td>

   <td width="34">1</td>

   <td width="18">1</td>

  </tr>

  <tr>

   <td width="293">                                                                           A4     0</td>

   <td width="34">1</td>

   <td width="34">71</td>

   <td width="18">71</td>

  </tr>

  <tr>

   <td width="293">                                                                           A2     0</td>

   <td width="34">1</td>

   <td width="34">71</td>

   <td width="18">71</td>

  </tr>

 </tbody>

</table>

<h1>Web-submission instructions</h1>

<ul>

 <li>First, type the following command, all on one line (replacing xxxxxxx with your student ID):</li>

</ul>

svn mkdir –parents -m “DDDM”

https://version-control.adelaide.edu.au/svn/axxxxxxx/2020/s2/dddm/assignment1

<ul>

 <li>Then, check out this directory and add your files: svn co https://version-control.adelaide.edu.au/svn/axxxxxxx/2020/s2/dddm/assignment1 cd assignment1 svn add AAGenerator.cpp svn add CAGenerator.cpp svn commit -m “assignment1 solution”</li>

 <li>Next, go to the web submission system at:</li>

</ul>

<a href="https://cs.adelaide.edu.au/services/websubmission/">https://cs.adelaide.edu.au/services/websubmission/</a>

Navigate to 2020, Semester 2, Distributed Databases and Data Mining, Assignment 1. Then, click Tab “Make Submission” for this assignment and indicate that you agree to the declaration. The automark script will then check whether your code compiles. You can make as many resubmissions as you like. If your final solution does not compile you will not get any marks for this solution.

<ul>

 <li><strong>Note:</strong>

  <ol>

   <li>The auto-marker script compiles and runs the two cpp files named “AAGenera-tor.cpp” and “CAGenerator.cpp” one by one.</li>

   <li>The auto-marker script will compile your AAGenerator.cpp and CAGenerator.cpp bythe following command:</li>

  </ol></li>

</ul>

g++ -std=c++11 AAGenerator.cpp -o runAA g++ -std=c++11 CAGenerator.cpp -o runCA

<ul>

 <li>Your AAGenerator.cpp should accept three input text files in the order of Attributes(att), Queries (query) and Access Frequencies (acc), which are randomly generated by the system, then output and print the required attribute affinity matrix (aa). Your CAGenerator.cpp should accept input affinity matrix (aa) provided by the system rather than reading your AAGenerator’s output AA, then output and print the clustered affinity matrix (CA) as the output. In this way of testing AA and CA separately, your marks will be maximized — you will receive marks for your correct CAGenerator coding even if your AAGenerator produces incorrect AA.</li>

</ul>

<ol>

 <li>The file path and the file name in your local machine will not work with our websub-mission system.</li>

</ol>
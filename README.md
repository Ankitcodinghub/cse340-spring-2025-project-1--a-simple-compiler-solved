# cse340-spring-2025-project-1--a-simple-compiler-solved



**<span style='color:red'>TO GET THIS SOLUTION VISIT:</span>** https://www.ankitcodinghub.com/product/cse340-spring-2025-project-1-a-simple-compiler-solved/

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;127697&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;5&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (5 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSE340 Spring 2025 Project 1- A Simple Compiler! Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">
            
<div class="kksr-stars">
    
<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
    
<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>
                

<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (5 votes)    </div>
    </div>
<h1>1&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Introduction</h1>
I will start with a high-level description of the project and its tasks, and in subsequent sections I will give a detailed description on how to achieve these tasks. The goal of this project is to implement a simple compiler for a simple programming language. To implement this simple compiler, you will write a recursive-descent parser and use some simple data structures to implement semantic checking and execute the input program. The input to your compiler has four parts:

<ol>
<li>The first part of the input is the TASKS section. It contains a list of one or more numbers of tasks to be executed by the compiler.</li>
<li>The second part of the input is the POLY section. It contains a list of polynomial declarations.</li>
<li>The third part of the input is the EXECUTE section. It contains a sequence of INPUT, OUTPUT and assignment statements.</li>
<li>The fourth part of the input is the INPUTS section. It contains a sequence of integers that will be used as the input to INPUT statements in the EXECUTE section.</li>
</ol>
Your compiler will parse the input and produces a syntax error message if there is a syntax error. If there is no syntax error, your compiler will analyze semantic errors. If there are no syntax and no semantic errors, your compiler will perform other semantic analyses if so specified by the tasks numbers in the TASKS section. If required, it will <em>also </em>execute the EXECUTE section and produces the output that should be produced by the OUTPUT statements.

The remainder of this document is organized as follows.

<ul>
<li>The second section describes the input format.</li>
<li>The third section describes the expected output when the syntax or semantics are not correct.</li>
<li>The fourth section describes the output when the program syntax and semantics are correct.</li>
<li>The fifth section describes the requirements for your solution.</li>
</ul>
<strong>Note</strong>: Nothing in this project is inherently hard, but it is larger than other projects that you have done in the past for other classes. The size of the project can make it feel unwieldy. To deal with the size of the project, it is important to have a good idea of what the requirements are. To do so, you should read this document a couple of times. Then, you should have an implementation plan. I make the task easier by providing an implementation guide that addresses some issues that you might encounter in implementing a solution. Once you have a good understanding and a good plan, you can start coding.

<h1>2&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Input Format</h1>
<h2>2.1&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Grammar and Tokens</h2>
The input of your program is specified by the following context-free grammar:

<table width="666">
<tbody>
<tr>
<td width="215">program</td>
<td width="35"><em>→</em></td>
<td width="415">tasks_sectionpoly_sectionexecute_sectioninputs_section</td>
</tr>
<tr>
<td width="215">tasks_section</td>
<td width="35"><em>→</em></td>
<td width="415">TASKSnum_list</td>
</tr>
<tr>
<td width="215">num_list</td>
<td width="35"><em>→</em></td>
<td width="415">NUM</td>
</tr>
<tr>
<td width="215">num_list</td>
<td width="35"><em>→</em></td>
<td width="415">NUMnum_list</td>
</tr>
<tr>
<td width="215">poly_section</td>
<td width="35"><em>→</em></td>
<td width="415">POLYpoly_decl_list</td>
</tr>
<tr>
<td width="215">poly_dec_list</td>
<td width="35"><em>→</em></td>
<td width="415">poly_decl</td>
</tr>
<tr>
<td width="215">poly_dec_list</td>
<td width="35"><em>→</em></td>
<td width="415">poly_declpoly_dec_list</td>
</tr>
<tr>
<td width="215">poly_decl</td>
<td width="35"><em>→</em></td>
<td width="415">poly_headerEQUALpoly_bodySEMICOLON</td>
</tr>
<tr>
<td width="215">poly_header</td>
<td width="35"><em>→</em></td>
<td width="415">poly_name</td>
</tr>
<tr>
<td width="215">poly_header</td>
<td width="35"><em>→</em></td>
<td width="415">poly_nameLPARENid_listRPAREN</td>
</tr>
<tr>
<td width="215">id_list</td>
<td width="35"><em>→</em></td>
<td width="415">ID</td>
</tr>
<tr>
<td width="215">id_list</td>
<td width="35"><em>→</em></td>
<td width="415">IDCOMMAid_list</td>
</tr>
<tr>
<td width="215">poly_name</td>
<td width="35"><em>→</em></td>
<td width="415">ID</td>
</tr>
<tr>
<td width="215">poly_body</td>
<td width="35"><em>→</em></td>
<td width="415">term_list</td>
</tr>
<tr>
<td width="215">term_list</td>
<td width="35"><em>→</em></td>
<td width="415">term</td>
</tr>
<tr>
<td width="215">term_list</td>
<td width="35"><em>→</em></td>
<td width="415">termadd_operatorterm_list</td>
</tr>
<tr>
<td width="215">term</td>
<td width="35"><em>→</em></td>
<td width="415">monomial_list</td>
</tr>
<tr>
<td width="215">term</td>
<td width="35"><em>→</em></td>
<td width="415">coefficientmonomial_list</td>
</tr>
<tr>
<td width="215">term</td>
<td width="35"><em>→</em></td>
<td width="415">coefficient</td>
</tr>
<tr>
<td width="215">monomial_list</td>
<td width="35"><em>→</em></td>
<td width="415">monomial</td>
</tr>
<tr>
<td width="215">monomial_list</td>
<td width="35"><em>→</em></td>
<td width="415">monomialmonomial_list</td>
</tr>
<tr>
<td width="215">monomial</td>
<td width="35"><em>→</em></td>
<td width="415">primary</td>
</tr>
<tr>
<td width="215">monomial</td>
<td width="35"><em>→</em></td>
<td width="415">primaryexponent</td>
</tr>
<tr>
<td width="215">primary</td>
<td width="35"><em>→</em></td>
<td width="415">ID</td>
</tr>
<tr>
<td width="215">primary</td>
<td width="35"><em>→</em></td>
<td width="415">LPARENterm_listRPAREN</td>
</tr>
<tr>
<td width="215">exponent</td>
<td width="35"><em>→</em></td>
<td width="415">POWERNUM</td>
</tr>
<tr>
<td width="215">add_operator</td>
<td width="35"><em>→</em></td>
<td width="415">PLUS</td>
</tr>
<tr>
<td width="215">add_operator</td>
<td width="35"><em>→</em></td>
<td width="415">MINUS</td>
</tr>
<tr>
<td width="215">coefficient</td>
<td width="35"><em>→</em></td>
<td width="415">NUM</td>
</tr>
<tr>
<td width="215">execute_section</td>
<td width="35"><em>→</em></td>
<td width="415">EXECUTEstatement_list</td>
</tr>
<tr>
<td width="215">statement_list</td>
<td width="35"><em>→</em></td>
<td width="415">statement</td>
</tr>
<tr>
<td width="215">statement_list</td>
<td width="35"><em>→</em></td>
<td width="415">statementstatement_list</td>
</tr>
<tr>
<td width="215">statement</td>
<td width="35"><em>→</em></td>
<td width="415">input_statement</td>
</tr>
<tr>
<td width="215">statement</td>
<td width="35"><em>→</em></td>
<td width="415">output_statement</td>
</tr>
<tr>
<td width="215">statement</td>
<td width="35"><em>→</em></td>
<td width="415">assign_statement</td>
</tr>
<tr>
<td width="215">input_statement</td>
<td width="35"><em>→</em></td>
<td width="415">INPUTIDSEMICOLON</td>
</tr>
<tr>
<td width="215">output_statement</td>
<td width="35"><em>→</em></td>
<td width="415">OUTPUTIDSEMICOLON</td>
</tr>
<tr>
<td width="215">assign_statement</td>
<td width="35"><em>→</em></td>
<td width="415">IDEQUALpoly_evaluationSEMICOLON</td>
</tr>
<tr>
<td width="215">poly_evaluation</td>
<td width="35"><em>→</em></td>
<td width="415">poly_nameLPARENargument_listRPAREN</td>
</tr>
<tr>
<td width="215">argument_list</td>
<td width="35"><em>→</em></td>
<td width="415">argument</td>
</tr>
<tr>
<td width="215">argument_list</td>
<td width="35"><em>→</em></td>
<td width="415">argumentCOMMAargument_list</td>
</tr>
<tr>
<td width="215">argument</td>
<td width="35"><em>→</em></td>
<td width="415">ID</td>
</tr>
<tr>
<td width="215">argument</td>
<td width="35"><em>→</em></td>
<td width="415">NUM</td>
</tr>
<tr>
<td width="215">argument</td>
<td width="35"><em>→</em></td>
<td width="415">poly_evaluation</td>
</tr>
<tr>
<td width="215">inputs_section</td>
<td width="35"><em>→</em></td>
<td width="415">INPUTSnum_list</td>
</tr>
</tbody>
</table>
The code that we provided has a class LexicalAnalyzer with methods GetToken() and peek(). Also, an expect() function is provided. Your parser will use the functions provided to peek()) at tokens or expect() tokens as needed. You must not change these provided functions; you just use them as provided. In fact, when you submit the code, you should not submit the files inputbuf.cc, (inputbuf.h, lexer.cc or lexer.h on gradescope; when you submit the code, the submission site will automatically provide these files, so it is important not to modify these files in your implementation.

To use the provided methods, you should first instantiate a lexer object of the class LexicalAnalyzer and call the methods on this instance. You should only instantiate one lexer object. If you try to instantiate more than one, this will result in errors.

The definition of the tokens is given below for completeness (you can ignore it for the most part if you want).

<table width="650">
<tbody>
<tr>
<td width="137">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; char&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; =</td>
<td width="513">a | b | … | z | A | B | … | Z | 0 | 1 | … | 9</td>
</tr>
<tr>
<td width="137">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; letter&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; =</td>
<td width="513">a | b | … | z | A | B | … | Z</td>
</tr>
<tr>
<td width="137">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; pdigit&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; =</td>
<td width="513">1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9</td>
</tr>
<tr>
<td width="137">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; digit&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; =</td>
<td width="513">0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9</td>
</tr>
<tr>
<td width="137">SEMICOLON</td>
<td width="513">= ;</td>
</tr>
<tr>
<td width="137">COMMA</td>
<td width="513">= ,</td>
</tr>
<tr>
<td width="137">PLUS</td>
<td width="513">= +</td>
</tr>
<tr>
<td width="137">MINUS</td>
<td width="513">= –</td>
</tr>
<tr>
<td width="137">POWER</td>
<td width="513">= ^</td>
</tr>
<tr>
<td width="137">EQUAL</td>
<td width="513">= =</td>
</tr>
<tr>
<td width="137">LPAREN</td>
<td width="513">= (</td>
</tr>
<tr>
<td width="137">RPAREN</td>
<td width="513">= )</td>
</tr>
<tr>
<td width="137">TASKS</td>
<td width="513">= (T).(A).(S).(K).(S)</td>
</tr>
<tr>
<td width="137">POLY</td>
<td width="513">= (P).(O).(L).(Y)</td>
</tr>
<tr>
<td width="137">EXECUTE</td>
<td width="513">= (E).(X).(E).(C).(U).(T).(E)</td>
</tr>
<tr>
<td width="137">INPUT</td>
<td width="513">= (I).(N).(P).(U).(T)</td>
</tr>
<tr>
<td width="137">OUTPUT</td>
<td width="513">= (O).(U).(T).(P).(U).(T)</td>
</tr>
<tr>
<td width="137">INPUTS</td>
<td width="513">= (I).(N).(P).(U).(T).(S)</td>
</tr>
<tr>
<td width="137">NUM</td>
<td width="513">= 0 | pdigit . digit*</td>
</tr>
<tr>
<td width="137">ID</td>
<td width="513">= letter . char*</td>
</tr>
</tbody>
</table>
What you need to do is write a parser to parse the input according to the grammar and produce a syntax error message if there is a syntax error. Your program will also check for semantic errors and, depending on the tasks list, will execute more semantic tasks. To achieve that, your parser will store the program in appropriate data structures that facilitate semantic analysis and allow your compiler to <em>execute </em>the statement list in the execute_section. For now, do not worry how that is achieved. I will explain that in detail, partly in this document and more fully in the implementation guide document.

<h2>2.2&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Examples</h2>
The following are examples of input (to your compiler) with corresponding outputs. The output will be explained in more detail in later sections. Each of these examples has task numbers 1 and 2 listed in the tasks_section. They have the following meanings:

<ul>
<li>The number 1 listed means that your program should perform syntax and semantic checking.</li>
<li>The number 2 listed means that your program should produce the output of the output statements if there are no syntax and no semantic errors.</li>
</ul>
<h3>EXAMPLE 1</h3>
TASKS

1 2

POLY

<ul>
<li>= x^2 + 1;</li>
<li>= x + 1;</li>
</ul>
EXECUTE

X = F(4); Y = G(2); OUTPUT X;

OUTPUT Y;

INPUTS

1 2 3 18 19

This example shows two polynomial declarations and a EXECUTE section in which the polynomials are evaluated with arguments 4 and 2 respectively. The output of the program will be

17 3

The sequence of numbers at the end (in the input_section) is ignored because there are no INPUT statements.

<h3>EXAMPLE 2</h3>
TASKS

1 2

POLY

<ul>
<li>= x^2 + 1;</li>
<li>= x + 1;</li>
</ul>
EXECUTE

INPUT X; INPUT Y;

X = F(X); Y = G(Y);

OUTPUT X;

INPUTS

1 2 3 18 19

This is similar to the previous example, but here we have two INPUT statements. The first INPUT statement reads a value for X from the sequence of numbers and X gets the value 1. The second INPUT statement reads a value for Y which gets the value 2. Here the output will be 2

Note that the values 3, 18 and 19 are not read and do not affect the execution of the program.

<h3>EXAMPLE 3</h3>
1:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; TASKS

2:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 2

3:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; POLY

4:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F = x^2 + 1;

5:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; G = x + 1;

6:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; EXECUTE

7:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT X; 8:&nbsp; INPUT Y;

9:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; X = F(X); 10:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Y = G(Y); 11:&nbsp; OUTPUT X;

12: INPUTS

13:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 2 3 18 19

Note that there are line numbers added to this example. These line numbers are not part of the input and are added only to refer to specific lines of the program. In this example, which looks almost the same as the previous example, there is a syntax error because there is a missing semicolon on line 4. The output of the program should be SYNTAX ERROR !!!!!&amp;%!!

<h3>EXAMPLE 4</h3>
1:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; TASKS

2:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 2

3:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; POLY

4:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F = x^2 + 1;

5:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; G(X,Y) = X Y^2 + X Y;

6:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; EXECUTE

7:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT Z; 8:&nbsp; INPUT W;

9:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; X = F(Z);

10:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Y = G(Z,W);

11:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; OUTPUT X;

12:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; OUTPUT Y;

12: INPUTS

13:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 2 3 18 19

In this example, the polynomial G has two variables which are given explicitly (in the absence of explicitly named variables, the variable is lower case x by default). The output is

2 6

<h3>EXAMPLE 5</h3>
1:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; TASKS

2:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 2

3:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; POLY

4:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F = x^2 + 1;

5:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; G(X,Y) = X Y^2 + X Z;

6:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; EXECUTE

7:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT Z; 8:&nbsp; INPUT W;

9:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; X = F(Z);

10:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Y = G(Z,W);

11:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; OUTPUT X;

12:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; OUTPUT Y;

12: INPUTS

13:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 2 3 18 19

This example is similar to the previous one but it has a problem. The polynomial G is declared with two variables X and Y but its equation (called poly_body in the grammar) has Z which is different from

X and Y. The output captures this error (see below for error codes and their format) Semantic Error Code 2: 5

<h1>3&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Tasks and their priorities</h1>
The task numbers specify what your program should do with the input program. Task 1 is one of the larger tasks and, but it is not graded as one big task. Task 1 has the following functionalities:

<ol>
<li>Syntax checking</li>
<li>Semantic error checkings</li>
</ol>
The other tasks, 2, 3, 4, 5 and 6 have the following functionalities:

<ul>
<li><strong>Task 2 – Output</strong>: Task 2 requires your compiler to produce the output that should be produced by the output statements of the program. .</li>
<li><strong>Task 3 – Variable used but not explicitly initialized</strong>: Task 3 requires your compiler to produce a warning about uninitialized variables. A variable is uninitialized when a variable appears on the right-hand side of an assignment statement without having previously appeared on the left-hand side of an assignment statement or in an INPUT statement. This will result in a warning message. However, it is not considered a semantic error. The execution can proceed assuming the variable is initially zero.</li>
<li><strong>Task 4 – Useless assignments</strong>: This happens when a variable value is calculated, but the variable is not used later in the right-hand side of an assignment or in an OUTPUT statement.</li>
<li><strong>Task 5 – Polynomial degree</strong>: This task requires that the degree of all the polynomials in the polynomial sections are calculated and outputted.</li>
</ul>
Detailed descriptions of these tasks and what the output should be for each of them is given in the sections that follow. The remainder of this section explains what the output of your program should be when multiple task numbers are listed in the tasks_section.

If task 1 is listed in the tasks_section, then task 1 should be executed. Remember that task 1 performs syntax error checking and semantic error checking. If the execution of task 1 results in an error, and task 1 is listed in the tasks_section, then your program should only output the error messages (as described below) and exits. If task 1 results in an error (syntax or semantic) no other tasks will be executed even if they are listed in the tasks_section. If task 1 is listed in the tasks_section and does not result in an error message, then task 1 produces no output. In that case, the outputs of the other tasks that are listed in tasks_section should be produced by the program. The order of these outputs should be according to the task numbers. So, first the output of task 2 is produced (if task 2 is listed in tasks_section), then the output of task 3 is produced (if task 3 is listed in tasks_section) and so on.

If task 1 is not listed in the tasks_section, task 1 still needs to be executed. If task 1’s execution results in an error, then your program should output nothing in this case. If task 1 is not listed and task 1’s execution does not result in an error, then the outputs of the other tasks that are listed in tasks_section should be produced by the program. The order of these outputs should be according to the task numbers. So, first the output of task 2 is produced, then the output of task 3 is produced (if task 3 is listed in tasks_section) and so on.

You should keep in mind that tasks are not necessarily listed in order in the tasks_section and they can even be repeated. For instance, we can have the following TASKS section: TASKS

1 3 4 1 2 3

In this example, some tasks are listed more than once. Later occurrences are ignored. So, the tasks_section above is equivalent to TASKS 1 2 3 4

In the implementation guide, I explain a simple way to read the list and sort the task numbers using a boolean array.

<h1>4&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Task 1 – Syntax and Semantic Checking</h1>
For task 1, your solution should detect syntax and semantic errors in the input program as specified in this section.

<h2>4.1&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Syntax Checking</h2>
If the input is not correct syntactically, your program should output SYNTAX ERROR !!!!!&amp;%!!

If there is syntax error, the output of your program should exactly match the output given above. No other output should be produced in this case, and your program should exit after producing the syntax error message. The provided parser.* skeleton files already have a function that produces the message above and exits the program.

<h2>4.2&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Semantic Checking</h2>
Semantic checking also checks for invalid input. Unlike syntax checking, semantic checking requires knowledge of the specific lexemes and does not simply look at the input as a sequence of tokens (token types). I start by explaining the rules for semantic checking. I also provide some examples to illustrate these rules.

<ul>
<li><strong>Polynomial declared more than once – Semantic Error Code 1</strong>. If the same polynomial_name is used in two or more different polynomial_header’s, then we have the error <em>polynomial declared more</em></li>
</ul>
<em>than once</em>. The output in this case should be of the form

Semantic Error Code 1: &lt;line no 1&gt; &lt;line no 2&gt; … &lt;line no k&gt;

where &lt;line no 1&gt; through &lt;line no k&gt; are the numbers of each of the lines in which a duplicate polynomial_name appears in a polynomial header. The numbers should be sorted from smallest to largest. For example, if the input is (recall that line numbers are not part of the input and are just for reference):

1:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; TASKS

2:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 3 4

3:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; POLY

4:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F1 =

5:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; x^2 + 1;

6:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F2 = x^2 + 1; 7:&nbsp;&nbsp;&nbsp;&nbsp; F1 = x^2 + 1;

8:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F3 = x^2 + 1;

9:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; G = x^2 + 1;

10:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F1 = x^2 + 1;

11:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; G(X,Y) = X Y^2 + X Y;

12: EXECUTE

13:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT Z; 14:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT W;

15:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; X = F1(Z);

16:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Y = G(W); 17:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; OUTPUT X;

18:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; OUTPUT Y;

19: INPUTS

20:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 2 3 18 19

then the output should be

Semantic Error Code 1: 7 10 11

because on each of these lines the name of the polynomial in question has a duplicate declaration. Note that only the line numbers for the duplicates are listed. The line number for the first occurrence of a name is not listed.

<ul>
<li><strong>Invalid monomial name – Semantic Error Code 2</strong>. There are two kinds of polynomials headers. In the first kind, only the polynomial name (ID) is given and no parameter list (id_list in the header) is given. In the second kinds, the header has the form polynomial_nameLPARENid_listRPAREN. In a polynomial with the first kind of header, the polynomial should be univariate (one variable) and the variable name should be lower case “x”. In a polynomials with the second kind of header, the id_list is the list variables that can appear in the polynomial body. An ID that appears in the body of a polynomial (in primary) should be equal to one of the variables of the polynomial. If that is not the case, we say that we have an <em>invalid monomial name error </em>and the output in this case should be of the form:</li>
</ul>
Semantic Error Code 2: &lt;line no 1&gt; &lt;line no 2&gt; … &lt;line no k&gt; where &lt;line no 1&gt; through &lt;line no k&gt; are the numbers of lines in which an invalid monomial name appears with one number printed per occurrence of an invalid monomial name. If there are multiple occurrences of an invalid monomial name on a line, the line number should be printed multiple times. The line numbers should be sorted from smallest to largest.

<ul>
<li><strong>Attempted evaluation of undeclared polynomial – Semantic Error Code 3</strong>. If there is no polynomial declaration with polynomial name which is the same as a polynomial name used in a polynomial evaluation, then we have <em>attempted evaluation of undeclared polynomial error</em>. In this case, the output should be of the form</li>
</ul>
Semantic Error Code 3: &lt;line no 1&gt; &lt;line no 2&gt; … &lt;line no k&gt;

where &lt;line no 1&gt; through &lt;line no k&gt; are the numbers of each of the lines in which a

polynomial_name appears in a polynomial_evaluation but for which there is no polynomial_declaration

with the same name. The line numbers should be listed from the smallest to the largest. For example if

the input is:

1:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; TASKS

2:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 3 4

3:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; POLY

4:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F1 = x^2 + 1; 5:&nbsp;&nbsp;&nbsp;&nbsp; F2 = x^2 + 1; 6:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F3 = x^2 + 1; 7:&nbsp;&nbsp;&nbsp;&nbsp; F4 = x^2 + 1; 8:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; G1 = x^2 + 1; 9:&nbsp;&nbsp;&nbsp; F5 = x^2 + 1;

10:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; G2(X,Y) = X Y^2 + X Y;

11: EXECUTE

12:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT Z; 13:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT W;

14:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; X = G(Z);

15:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Y = G2(Z,W);

16:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; X = F(Z);

17:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Y = G2(Z,W);

18: INPUTS

19:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 2 3 18 19

then the output should be

Semantic Error Code 3: 14 16

Because on line 14, there is an evaluation of polynomial G but there is no declaration for polynomial G and on line 16, there is an evaluation of polynomial F but there is no declaration of polynomial F.

<ul>
<li><strong>Wrong number of arguments – Semantic Error Code 4</strong>. If the number of arguments in a polynomial evaluation is different from the number of parameters in the polynomial declaration, then we say that we have <em>wrong number of arguments error </em>and the output should be of the form: Semantic Error Code 4: &lt;line no 1&gt; &lt;line no 2&gt; … &lt;line no k&gt;</li>
</ul>
where &lt;line no 1&gt; through &lt;line no k&gt; are the numbers of each of the lines in which polynomial_name appears in a polynomial_evaluation but the number of arguments in the polynomial evaluation is different from the number of parameters in the corresponding polynomial declaration. The line numbers should be listed from the smallest to the largest. For example if the input is:

1:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; TASKS

2:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 3 4

3:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; POLY

4:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F1 = x^2 + 1;

5:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F2 = x^2 + 1; 6:&nbsp;&nbsp;&nbsp;&nbsp; F3 = x^2 + 1; 7:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F4 = x^2 + 1; 8:&nbsp;&nbsp;&nbsp;&nbsp; G1 = x^2 + 1; 9:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F5 = x^2 + 1;

10:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; G2(X,Y) = X Y^2 + X Y;

11: EXECUTE

12:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT Z; 13:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT W;

14:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; X = G2(X,Y, Z);

15:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Y = G2(Z,W);

16:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; X = F1(Z);

17:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Y = F5(Z,Z);

18:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Y = F5(Z,Z,W);

19: INPUTS

20:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 2 3 18 19

then the output should be

Semantic Error Code 4: 14 17 18

You can assume that an input program will have only one kind of semantic errors. So, for example, if a test case has Semantic Error Code 2, it will not have any other kind of semantic errors.

<h1>5&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Task 2 – Program Output</h1>
For task 2, your program should output the results of all the polynomial evaluations in the propram. In this section I give a precise definition of the meaning of the input and the output that your compiler should generate. In a separate document that I will upload a little later, I will give an implementation guide that will help you plan your solution. You do not need to wait for the implementation guide to write the parser!

<h2>5.1&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Variables and Locations</h2>
The program uses names to refer to variables in the EXECUTE section. For each variable name, we associate a unique locations that will hold the value of the variable. This association between a variable name and its location is assumed to be implemented with a function location that takes a string as input and returns an integer value. We assume that there is a variable mem which is an array with each entry corresponding to one variable. <strong>All variables should be initialized to 0 (zero)</strong>.

To allocate mem entries to variables, you can have a simple table or map (which I will call the <em>location table</em>) that associates a variable name with a location. As your parser parses the input program, if it encounters a variable name in an input_statement, it needs to determine if this name has been previously encountered or not by looking it up in the location table. If the name is a new variable name, a new location needs to be associated with it, and the mapping from the variable name to the location needs to be added to the location table. To associate a location with a variable, you can simply keep a counter that tells you how many locations have been used (associated with variable names). Initially, the counter is 0. The first variable will have location 0 associated with it (will be stored in mem[0]), and the counter is incremented to become 1. The next variable will have location 1 associated with it (will be stored in mem[1]), and the counter is incremented to become 2 and so on.

For example, if the input program is

1:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; TASKS

2:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 2

3:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; POLY

4:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F1 = x^2 + 1;

5:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F2(x,y,z) = x^2 + y + z + 1;

6:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F3(y) = y^2 + 1;

7:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F4(x,y) = x^2 + y^2;

8:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; G1 = x^2 + 1; 9:&nbsp;&nbsp;&nbsp; F5 = x^2 + 1;

10:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; G2(X,Y,Z,W) = X Y^2 + X Z + W + 1;

11: EXECUTE

12:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT X; 13:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT Z;

14:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Y = F1(Z);

15:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; W = F2(X,Z,Z);

16:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; OUTPUT W;

17:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; OUTPUT Y;

18:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT X; 19:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT Y; 20:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT Z;

21:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Y = F3(X);

22:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; W = F4(X,Y);

23:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; OUTPUT W;

24:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; OUTPUT Y;

25:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT X; 26:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT Z; 27:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT W;

28:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; W = G2(X,Z,W,

29:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Z);

30: INPUTS

31:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 2 3 18 19 22 33 12 11 16

Then the locations of variables will be

X 0 Z 1 Y 2 W 3

<h2>5.2&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Statements</h2>
We explain the semantics of the four kinds of statements in the program.

<h3>5.2.1&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Input statements</h3>
Input statements get their input from the sequence of inputs. We refer to i’th value that appears in inputs as i’th input. The i’th input statement in the program of the form INPUT X is equivalent to:

mem[location(“X”)] = i’th input

<h3>5.2.2&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Output statements</h3>
Output statements have the form OUTPUT ID where the lexeme of the token ID is a variable name. This is the <em>output variable </em>of the output statement. Output statements print the values of their OUTPUT variables. If the output statement has the form OUTPUT X; , its effect is equivalent to:

cout &lt;&lt; mem[location(“X”)] &lt;&lt; endl;

<strong>Note that each output statement produces its output on a separate line.</strong>

<h3>5.2.3&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Assignment statements</h3>
Assignment statements have the form:

ID EQUAL poly_evaluation SEMICOLON

If the lexeme of the ID token of an assign_statement is “X”, and the poly_evaluation of the assign_statement has value v (see below for the value of a polynomial evaluation), then the assign statement execution will have an effect equivalent to mem[location(“X”)] = v;

<h3>5.2.4&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Polynomial Evaluation</h3>
The polynomial evaluation depends on the evaluation of arguments and the correspondence between the arguments in polynomial evaluation and the parameters in the polynomial declaration.

<strong>Argument Evaluation.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </strong>The <em>value </em>of a variable X at a given point in the program is equal to the last value assigned to X before that point (a variable is assigned a value either in an input_statement statement or in an assign_statement) . If there is no prior assignment to X before that point, then the value of X is

0 (zero). The definition of what an argument evaluates to depends on the definition of what a polynomial evaluates to because an argument can be a polynomial evaluation. An argument is evaluated as follows:

<ul>
<li>If the argument is an ID whose lexeme is “X”, then it evaluates to the value of “X” at that point.</li>
<li>If the argument is a polynomial evaluation, then it evaluates to what the polynomial evaluates to (see below).</li>
</ul>
<strong>Correspondence Between Arguments and Parameters. </strong>In a polynomial declaration, the list of parameters is given by the id_list in the header or if the header has no id_list, then the parameter is the unique variable “x” (lower case). In a polynomial evaluation, the argument list is given by the argument_list.

We say that the i’th argument in a polynomial evaluation <em>corresponds to </em>the i’th parameter of the polynomial declaration.

<strong>Evaluation of a coefficient.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </strong>A coefficient whose lexeme is L evaluates to the integer represented by L.

<strong>Evaluation of an exponent.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </strong>An exponent whose lexeme is L evaluates to the integer represented by L.

<strong>Evaluation of a monomial.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </strong>There are a number of cases to consider

<ul>
<li>A monomial of the form ID whose lexeme is “X” evaluates to the argument corresponding to “X”</li>
<li>A monomial of the form IDexponent where the lexeme of the ID is “X” evaluates to <em>v<sup>e </sup></em>where <em>e </em>is the value that the exponent evaluate to and <em>v </em>is the value that the argument corresponding to “X” evaluates to.</li>
</ul>
<strong>Evaluation of a monomial_list .&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </strong>A monomial_list of the form monomial evaluates to the value that monomial evaluates to. A monomial_list of the form monomialmonomial_list’ evaluates to the product of <em>v </em>(the value that monomial evaluates to) and <em>v<sup>0 </sup></em>(the value that monomial_list’ evaluates to).

<strong>Evaluation of a term.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </strong>A term of the form coefficientmonomial_list, where coefficient evaluates to <em>c </em>and monomial_list evaluates to <em>v</em>, evaluates to <em>c × v </em>(the product of <em>c </em>and <em>v</em>).

<strong>Evaluation of a term_list. </strong>A term_list of the form term evaluate to the value that term evaluates to. A term_list of the form termadd_operatorterm_list’, where term evaluates to <em>v </em>and term_list’ evaluates to v’, evaluates to <em>v </em>+ <em>v<sup>0 </sup></em>if the add_operator is PLUS and to <em>v − v<sup>0 </sup></em>if the add_operator is MINUS.

<strong>Evaluation of a polynomial_body.&nbsp;&nbsp;&nbsp; </strong>A polynomial_body of the form term_list evaluates to the value that the term_list evaluates to.

<strong>Evaluation of a polynomial. </strong>A polynomial evaluates to the value that its polynomial_body evaluates to.

<h2>5.3&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Assumptions</h2>
You can assume that the following semantic errors are not going to be tested

<ol>
<li>You can assume that if there is a polynomial declaration with a given polynomial name, then there is no variable with the same name in the program.</li>
<li>If you want to use an array for the mem variable, you can use an array of size 1000 which should be enough for all test cases, but make sure that your code handles overflow (more than 1000 variables in the program) because that is good programming practice.</li>
</ol>
<h1>6&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Task 3 – Variable used before being initialized</h1>
<strong>Uninitialized argument. Warning Code 1</strong>. If an argument in an argument_list in a polynomial_evaluation does not appear in an input_statement nor on the lefthand side of an assignment statement before the polynomial evaluation, then we say that we have an <em>uninitialized argument</em>

<em>warning </em>and the output should be of the form:

Warning Code 1: &lt;line no 1&gt; &lt;line no 2&gt; … &lt;line no k&gt; where &lt;line no 1&gt; through &lt;line no k&gt; are the numbers of each of the lines in which an argument appears in a polynomial_evaluation but for which: (1) which there is no previous assign_statement in which the argument appears on the lefthand side of the EQUAL sign and (2) there is no previous input_statement in which the argument appears. The line numbers should be listed from the smallest to the largest. For example,

if the input is:

1:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; TASKS

2:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 2 3

3:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; POLY

4:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F1 = x^2 + 1;

5:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F2(x,y,z) = x^2 + y + z + 1;

6:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F3(y) = y^2 + 1;

7:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F4(x,y) = x^2 + y^2;

8:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; G1 = x^2 + 1; 9:&nbsp;&nbsp;&nbsp; F5 = x^2 + 1;

10:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; G2(X,Y,Z,W) = X Y^2 + X Z + W + 1;

11: EXECUTE

12:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT X; 13:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT Z;

14:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Y = F1(Z);

15:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; W = F2(W,Z, W);

16:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT Y; 17:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT Z;

18:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Y = F4(X,Q); 19:&nbsp;&nbsp;&nbsp; W = F4(X,Y);

20:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; W = F2(W, P, P);

21:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; OUTPUT Y;

22:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT X;

23:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; W = G2(X,Z,W,

24:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Z);

25: INPUTS

26:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 5 2 3 18 19 22 33 12 11 16

then the output will be

25

Warning Code 1: 15 15 18 20 20

We first note that there is a 25 printed before the warning message. This is the output of the program (produced in line 21). Notice how the calculation is performed using value 5 for X (which is read from INPUTS on line 12) and value 0 for Q ( initial value 0 for Q because Q is not initialized). The output of the program should be produced in this case because there are no syntax and no semantic errors, and 2 appears in the TASKS section, so Task 2 should be executed.

Now, we explain the warning message. Notice that line 15 is repeated in the output because both W’s on line

15 are not initialized before they appear in the polynomial evaluation F2(W,Z,W). Line 18 is also listed in the warning message because in line 18, Q is used in the evaluation of F4(X,Q) without previously being initialized. Line 20 is repeated in the output because P which is used twice in the calculation of F2(W,P,P) without being previously initialized. Finally, note that there is no warning for lines 23 and 24 because all arguments are previously initialized: X on line 22, Z on line 17 and W on line 20.

<h1>7&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Task 4 – Useless assignments</h1>
A useless assignment occurs if a variable is assigned a value in an assignment statement, but the variable is not used later on the righthand side of an assignment in an assign_statement or in an output_statement.

The definition requires some explanation. Consider the following program:

1:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; TASKS

2:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 4

3:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; POLY

4:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F = 2x + 1;

5:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; EXECUTE

6:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; X = F(5); 7:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; X = F(6); 8:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; OUTPUT X; 9:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; X = F(7); 10:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; X = F(X);

11:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT X;

12:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; OUTPUT X;

13:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUTS

14:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2 4 6

We examine each assignment statement in the program.

Line 6: X = F(5); The value calculated in this statement is not used later in an output_statement or in an assign_statement because the next statement on line 7 overwrites the calculated value. Line 7: X = F(6); The value calculated in this statement is used by the output statement that appears on line 8.

Line 9: X = F(7); The value calculated in this statement appears on the right-hand side of the assign_statement on line 10, so the assignment is not useless.

Line 10: X = F(X); The value calculated in this statement is not used later in an output_statement or in an assign_statement because it is immediately followed by INPUT X; which overwrites the value of X.

In general, we can define useless assignments as follows. We say that a statement <em>defines </em>a variable x if it is of the form INPUT x; or if it is of the form x = poly_evaluations ; We say that a statement <em>uses </em>a variable x if the statement is of the form OUTPUT x; or if the statement is of the form ID = poly_evaluation ; and x appears in poly_evaluation as an argument.

Given the statement list stmt<sub>1 </sub>stmt<sub>2 </sub><em>… </em>stmt<em><sub>k</sub></em>, if stmt<em><sub>i </sub></em>has the form x = poly_evaluations ; , we say that stmt<em><sub>i </sub></em>is a useless assignment statement if stmt<em><sub>i </sub></em>is the last statement in the list, or stmt<em><sub>i</sub></em><sub>+1 </sub><em>defines </em>x, or stmt<em><sub>i</sub></em><sub>+1 </sub>does not <em>use </em>x and stmt<em><sub>i </sub></em>is useless in the sequence stmt<sub>1 </sub>stmt<sub>2 </sub><em>… </em>stmt<em><sub>i </sub></em>stmt<em><sub>i</sub></em><sub>+2 </sub><em>… </em>stmt<em><sub>k</sub></em>

If the program has useless assignments, then its output should be of the form: Warning Code 2: &lt;line no 1&gt; &lt;line no 2&gt; … &lt;line no k&gt;

where &lt;line no 1&gt; through &lt;line no k&gt; are the numbers of each of the lines that contains a useless assignment statement as defined above. The line numbers should be listed from the smallest to the largest, and you can assume that useless assignment statements are not split across multiple lines.

<h1>8&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Task 5 – Polynomial degree</h1>
This tasks requires that the degree of polynomials in the polynomial sections be calculated and outputted. The degree of a polynomial is defined as follows:

<ol>
<li>The degree of a primary of the form ID is 1.</li>
<li>The degree of a primary of the form LPARENterm_listRPAREN is equal to the degree of term_list.</li>
<li>The degree of a monomial of the form primary is equal to the degree of primary.</li>
<li>The degree of a monomial of the form primaryexponent is equal to the degree of primary times the value of the exponent.</li>
<li>The value of an exponent of the form POWERNUM is equal to the value of NUM, which is the integer that corresponds to the lexeme of NUM.</li>
<li>The degree of a monomial list of the form monomial is equal to the degree of the monomial.</li>
<li>The degree of a monomial list of the form monomialmonomial_list is equal to the sum of the degree of the monomial and the degree of monomial_list.</li>
<li>The degree of a term of the form coefficient is equal to 0 (zero).</li>
<li>The degree of a term which is of the form coefficientmonomial_list is equal to the degree of the monomial_list.</li>
<li>The degree of a term which is of the form monomial_list is equal to the degree of the monomial_list.</li>
<li>The degree of a term list of the form term is equal to the degree of term.</li>
<li>The degree of a term list of the form termadd_operatorterm_list is equal to the maximum of the degree of term and the degree of term_list.</li>
</ol>
If there are no syntax and no semantic errors, the output for this task should have the form

&lt;poly 1&gt;: &lt;degree 1&gt; &lt;poly 2&gt;: &lt;degree 2&gt;

&lt;poly 3&gt;: &lt;degree 3&gt; …

&lt;poly k&gt;: &lt;degree k&gt; where &lt;poly i&gt; is the name of the i’th polynomial and &lt;degree i&gt; is the degree of the i’th polynomial.

For example, if the input is:

1:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; TASKS

2:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 2 5

3:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; POLY

4:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F1 = x^2x + x^3x^1;

5:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F2(x,y,z) = x^2 + y + z + 1;

6:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F3(y) = y^2 + 1;

7:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F4(x,y) = x^2 + y^2;

8:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; G1(x,y,z,w) = x^2 y z w + x^2 y^2 z w + 1;

9:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; F5 = x^2 + 1;

10:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; G2(X,Y,Z,W) = X Y^2 + X Z + W + 1;

11: EXECUTE

12:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT X; 13:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT Z;

14:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Y = F1(Z);

15:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; W = F2(W,Z, W);

16:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT Y; 17:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT Z;

18:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Y = F4(X,Q); 19:&nbsp;&nbsp;&nbsp; W = F4(X,Y);

20:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; W = F2(W, P, P);

21:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; OUTPUT Y;

22:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; INPUT X;

23:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; W = G2(X,Z,W,

24:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Z);

25: INPUTS

26:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 5 2 3 18 19 22 33 12 11 16

The output will be:

25

F1: 4 F2: 2 F3: 2 F4: 2 G1: 6 F5: 2 G2: 3

By now, you should know why the output has 25 on the first line.

<h1>9&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Requirements</h1>
You should write a program to generate the correct output for a given input as described above. You should start by writing the parser and make sure that it correctly parses the input before attempting to implement the rest of the project.

You will be provided with a number of example test cases. These test cases are not meant to be complete or even close to complete. They are only provided as examples to complement the project description. It is still your responsibility to make sure that your implementation satisfies the requirements given in this document, and you should develop your own test cases to do so.

<h1>10&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Instructions</h1>
Follow these steps:

<ul>
<li>Read this document carefully.</li>
<li>When the implementation guide is posted, read it carefully. It has detailed explanations on how to approach the implementation.</li>
<li>Download the lexer.cc, lexer.h, inputbuf.cc and inputbuf.h files accompanying this project description and familiarize yourself with the provided functions.</li>
<li>Design a solution before you start coding. It is really very important to have a clear overall picture of what the project entails before you start coding. Deciding on data structures and how you will use them is crucial. One possible exception is the parser, which you can and should write first before the rest of the solution.</li>
<li>Write your code and make sure to compile your code using GCC (4:11.2.0) on <strong>Ubuntu 22.04 </strong>(Ubuntu).</li>
</ul>
If you want to test your code on your personal machine, you should install a virtual machine with

Ubuntu 22.04 and the correct version of GCC on it. You will need to use the g++ command to compile your code in a terminal window. See section 12 for more details on how to compile using GCC. <strong>You are required to compile and test your code on Ubuntu using the GCC compiler</strong>, but you are free to use any IDE or text editor on any platform while developing your code as long as you compile it and test it on Ubuntu/GCC before submitting it.

<ul>
<li>Test your code to see if it passes the provided test cases. You will need to extract the test cases from the zip file and run the provided test script test1.sh. See section 12 for more details.</li>
<li>Develop your own test cases and test your program on them.</li>
<li>Submit your code through gradescope.</li>
<li>You are allowed an unlimited number of submissions, but it is your responsibility to activate the submission that should count for your grade. If have a submission with a grade of 90 and another submission with a grade of 80. You should make sure to activate the older submission if you want it to count. Activating older submissions is also allowed during the late submission period. You can continue on working to improve your grade, but you can revert to an earlier grade if you want by activating an earlier submission.</li>
</ul>
<h2>Keep in mind that</h2>
<ul>
<li>You should use C++11, no other programming languages or versions of C++ are allowed.</li>
<li><strong>All programming assignments in this course are individual assignments. Students must complete the assignments on their own.</strong></li>
<li>You should submit your code through gradescope; no other mode of submission will be accepted.</li>
<li>You should familiarize yourself with the Ubuntu environment and the GCC compiler. Programming assignments in this course are different from assignments in other classes.</li>
</ul>
<h1>11&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Evaluation</h1>
Submissions are evaluated using automated test cases on gradescope. To receive credit for parsing, your submission should pass ALL the parsing test cases. For other categories, your grade will be proportional to the number of test cases that your submission passes.If your code does not compile on gradescope, you will not receive any points even if it runs correctly in a different environment (Windows/Visual Studio for example). Here is the grade breakdown for the various categories:

<ol>
<li><strong>Task 1 – Parsing: 30%</strong>. There is no partial credit for parsing. Your program should pass <strong>ALL </strong>the parsing test cases to get credit for parsing, otherwise no credit will be given for parsing.</li>
<li><strong>Task 1 – Semantic Error Code 1: 7.5%</strong>. The grade for this category will be proportional to the number of test cases that are correctly handled by your program.</li>
<li><strong>Task 1 – Semantic Error Code 2: 7.5%</strong>. The grade for this category will be proportional to the number of test cases that are correctly handled by your program.</li>
<li><strong>Task 1 – Semantic Error Code 3: 7.5%</strong>. The grade for this category will be proportional to the number of test cases that are correctly handled by your program.</li>
<li><strong>Task 1 – Semantic Error Code 4: 7.5%</strong>. The grade for this category will be proportional to the number of test cases that are correctly handled by your program.</li>
<li><strong>Task 2 – Program Output: 20%</strong>. The grade for this category will be proportional to the number of test cases that are correctly handled by your program.</li>
<li><strong>Task 3 – Variable used before being initialized: 10%</strong>. The grade for this category will be proportional to the number of test cases that are correctly handled by your program.</li>
<li><strong>Task 4 – Useless assignments: 10%</strong>. The grade for this category will be proportional to the number of test cases that are correctly handled by your program.</li>
<li><strong>Task 5 – Polynomial degree: 10%</strong>. The grade for this category will be proportional to the number of test cases that are correctly handled by your program.</li>
</ol>
<h1>12&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; General instructions for all programming assignments</h1>
<strong>NOTE: This section applies to all programming assignments.</strong>

You should use the instructions in the following sections to compile and test your programs for all programming assignments in this course.

<h2>12.1&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Compiling your code with GCC</h2>
You should compile your programs with the GCC compilers. GCC is a collection of compilers for many programming languages. There are separate commands for compiling C and C++ programs. Use the g++ command to compile C++ programs

Here is an example of how to compile a simple C++ program:

$ g++ test_program.cpp

If the compilation is successful, it will generate an executable file named a.out in the same directory (folder) as the program. You can change the executable file name by using the -o option. For example, if you want the executable name to be hello.out, you can execute

$ g++ test_program.cpp -o hello.out

To enable C++11, with g++, which you should do for projects in this class, use the -std=c++11 option:

$ g++ -std=c++11 test_program.cpp -o hello.out

The following table summarizes some useful compiler options for g++:

<table width="378">
<tbody>
<tr>
<td width="86">Option</td>
<td width="292">Description</td>
</tr>
<tr>
<td width="86">-o path</td>
<td width="292">Change the filename of the generated artifact</td>
</tr>
<tr>
<td width="86">-g</td>
<td width="292">Generate debugging information</td>
</tr>
<tr>
<td width="86">-ggdb</td>
<td width="292">Generate debugging information for use by GDB</td>
</tr>
<tr>
<td width="86">-Wall</td>
<td width="292">Enable most warning messages</td>
</tr>
<tr>
<td width="86">-std=c++11</td>
<td width="292">Compile C++ code using 2011 C++ standard</td>
</tr>
</tbody>
</table>
<h3>Compiling projects with multiple files</h3>
If your program is written in multiple source files that should be linked together, you can compile and link all files together with one command:

$ g++ file1.cpp file2.cpp file3.cpp

Or you can compile them separately and then link:

$ g++ -c file1.cpp $ g++ -c file2.cpp $ g++ -c file3.cpp

$ g++ file1.o file2.o file3.o

The files with the .o extension are object files but are not executable. They are linked together with the last statement (g++ file1.o file2.o file3.o) and the final executable will be a.out.

<h2>12.2&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Testing your code on Ubuntu</h2>
Your programs should not explicitly open any file. You can only use the <strong>standard input </strong>and <strong>standard output </strong>in C++. The provided lexical analyzer already reads the input from standard input and you should not modify it. In C++, standard input is std::cin and standard output is std::cout. In C++, any output that your program produces should be done with cout. To read input from a file or produce output to a file, we use IO redirection outside the program. The following illustrates the concept.

Suppose we have an executable program a.out, we can run it by issuing the following command in a terminal (the dollar sign is not part of the command):

$ ./a.out

If the program expects any input, it waits for it to be typed on the keyboard and any output generated by the program will be displayed on the terminal screen.

To get the input to the program from a file, we can redirect the standard input to a file:

$ ./a.out &lt; input_data.txt

Now, the program will not wait for keyboard input, but rather read its input from the specified file as if the file input_data.txt is standard input. We can redirect the output of the program as well: $ ./a.out &gt; output_file.txt

In this way, no output will be shown in the terminal window, but rather it will be saved to the specified file<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>.

Finally, it’s possible to do redirection for standard input and standard output simultaneously. For example,

$ ./a.out &lt; input_data.txt &gt; output_file.txt will read standard input from input_data.txt and produces standard output to output_file.txt.

Now that we know how to use standard IO redirection, we are ready to test the program with test cases.

<h3>Test Cases</h3>
For a given input to your program, there is an <em>expected </em>output which is the correct output that should be produced for the given input. So, a test case is represented by two files:

<ul>
<li>txt</li>
<li>txt.expected</li>
</ul>
The input is given in test_name.txt and the expected output is given in test_name.txt.expected.

To test a program against a single test case, first we execute the program with the test input data:

$ ./a.out &lt; test_name.txt &gt; program_output.txt

With this command, the output generated by the program will be stored in program_output.txt. To see if the program generated the correct expected output, we need to compare program_output.txt and test_name.txt.expected. We do that using the diff command which is a command to determine differences between two files:

$ diff -Bw program_output.txt test_name.txt.expected

If the two files are the same, there should be no difference between them. The options -Bw tell diff to ignore whitespace differences between the two files. If the files are the same (ignoring the whitespace differences), we should see no output from diff, otherwise, diff will produce a report showing the differences between the two files.

We consider that the test <strong>passed </strong>if diff could not find any differences, otherwise we consider that the test <strong>failed</strong>.

Our grading system uses this method to test your submissions against multiple test cases. In order to avoid having to type the commands shown above for running and comparing outputs for each test case manually, we provide you with a script that automates this process. The script name is test1.sh. test1.sh will make your life easier by allowing you to test your code against multiple test cases with one command.

Here is how to use test1.sh to test your program:

<ul>
<li>Store the provided test cases zip file in the same directory as your project source files</li>
<li>Open a terminal window and navigate to your project directory</li>
<li>Unzip the test archive using the unzip command: bash $ unzip tests.zip</li>
</ul>
This will create a directory called tests

<ul>
<li>Store the test1.sh script in your project directory as well</li>
<li>Make the script executable: bash $ chmod +x test1.sh</li>
<li>Compile your program. The test script assumes your executable is called a.out</li>
<li>Run the script to test your code: bash $ ./test1.sh</li>
</ul>
The output of the script should be self explanatory. To test your code after you make changes, you will just perform the last two steps (compile and run test1.sh).

<a href="#_ftnref1" name="_ftn1">[1]</a> Programs have access to another standard stream which is called standard error e.g. std::cerr in C++. Any such output is still displayed on the terminal screen. It is possible to redirect standard error to a file as well, but we will not discuss that here

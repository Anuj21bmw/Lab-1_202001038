# Lab-7_202001038
ANUJ MEENA
Section A:

Enlist which set of test cases have been identified using Equivalence Partitioning and Boundary Value Analysis separately.
Modify your programs such that it runs on eclipse IDE, and then execute your test suites on the program. While executing your input data in a program, check whether the identified expected outcome (mentioned by you) is correct or not. The solution of each problem must be given in the format as follows: Tester Action and Input Data Expected Outcome Equivalence Partitioning a, b, c An Error message a-1, b, c Yes Boundary Value Analysis a, b, c-1 Yes For details you may also refer to an example: Testing a simple program Programs:
P1. The function linearSearch searches for a value v in an array of integers a. If v appears in the array a, then the function returns the first index i, such that a[i] == v; otherwise, -1 is returned. int linearSearch(int v, int a[]) { int i = 0; while (i < a.length) { if (a[i] == v) return(i); i++; } return (-1); }

Tester Action and Input Data Expected Outcome

Ans:- Equivalence Partitioning:

Invalid input: day < 1 or day > 31 or month < 1 or month > 12 or year < 1900 or year > 2015: An error message should be displayed indicating that the input is invalid. Valid input: day, month, year are within valid ranges: If the input date is not the minimum valid date (January 1, 1900), then the function should return the previous date. If the input date is the minimum valid date, then an error message should be displayed indicating that there is no previous date. Boundary Value Analysis:

Invalid input: day = 0, month = 1, year = 1900: An error message should be displayed indicating that the input is invalid. day = 1, month = 0, year = 1900: An error message should be displayed indicating that the input is invalid. day = 1, month = 1, year = 1899: An error message should be displayed indicating that the input is invalid. day = 32, month = 1, year = 1900: An error message should be displayed indicating that the input is invalid. day = 31, month = 2, year = 1900: An error message should be displayed indicating that the input is invalid. day = 29, month = 2, year = 1900: An error message should be displayed indicating that the input is invalid. day = 31, month = 4, year = 1900: An error message should be displayed indicating that the input is invalid. day = 31, month = 6, year = 1900: An error message should be displayed indicating that the input is invalid. day = 31, month = 9, year = 1900: An error message should be displayed indicating that the input is invalid. day = 31, month = 11, year = 1900: An error message should be displayed indicating that the input is invalid. day = 30, month = 2, year = 1904: An error message should be displayed indicating that the input is invalid. Valid input: day = 1, month = 1, year = 1900: An error message should be displayed indicating that there is no previous date. day = 2, month = 1, year = 1900: The function should return the date (January 1, 1900). day = 1, month = 2, year = 1900: The function should return the date (January 31, 1899). day = 1, month = 3, year = 1900: The function should return the date (February 28, 1900). day = 28, month = 2, year = 1900: The function should return the date (February 27, 1900). day = 1, month = 4, year = 1900: The function should return the date (March 31, 1900). day = 1, month = 5, year = 1900: The function should return the date (April 30, 1900). day = 1, month = 6, year = 1900: The function should return the date (May 31, 1900). day = 1, month =

P2. The function countItem returns the number of times a value v appears in an array of integers a. int countItem(int v, int a[]) { int count = 0; for (int i = 0; i < a.length; i++) { if (a[i] == v) count++; } return (count); }

Ans:- Equivalence Partitioning:

Inputs:

Value v Array a Equivalence Classes:

Valid value v, non-empty array a with v appearing in a Valid value v, non-empty array a with v not appearing in a Valid value v, empty array a Invalid value v (e.g. null) Invalid array a (e.g. null) Test Suite:

Valid value v, non-empty array a with v appearing in a Input: v = 5, a = {2, 5, 7, 5, 9, 5} Expected Output: 3 Valid value v, non-empty array a with v not appearing in a Input: v = 4, a = {2, 5, 7, 3, 9, 1} Expected Output: 0 Valid value v, empty array a Input: v = 6, a = {} Expected Output: 0 Invalid value v Input: v = null, a = {2, 5, 7, 3, 9, 1} Expected Output: error message Invalid array a Input: v = 4, a = null Expected Output: error message Boundary Value Analysis:

Inputs:

Value v Array a Boundary Tests:

Valid value v, non-empty array a with v appearing once Input: v = 5, a = {2, 5, 7, 3, 9, 1} Expected Output: 1 Valid value v, non-empty array a with v appearing multiple times Input: v = 5, a = {2, 5, 7, 5, 9, 1, 5} Expected Output: 3 Valid value v, non-empty array a with v not appearing in a Input: v = 4, a = {2, 5, 7, 3, 9, 1} Expected Output: 0 Valid value v, empty array a Input: v = 6, a = {} Expected Output: 0 Invalid value v (null) Input: v = null, a = {2, 5, 7, 3, 9, 1} Expected Output: error message Invalid array a (null) Input: v = 4, a = null Expected Output: error message Program:

public class CountItem { public static int countItem(int v, int a[]) { if (v == null || a == null) { throw new IllegalArgumentException("Invalid input"); } int count = 0; for (int i = 0; i < a.length; i++) { if (a[i] == v) { count++; } } return count; } }

P3. The function binarySearch searches for a value v in an ordered array of integers a. If v appears in the array a, then the function returns an index i, such that a[i] == v; otherwise, -1 is returned. Assumption: the elements in the array are sorted in non-decreasing order. int binarySearch(int v, int a[]) { int lo,mid,hi; lo = 0; hi = a.length-1; while (lo <= hi) { mid = (lo+hi)/2; if (v == a[mid]) return (mid); else if (v < a[mid]) hi = mid-1; else lo = mid+1; } return(-1); }

Ans:- Equivalence Partitioning:

Equivalence partitioning is a black-box testing technique that divides the input domain of a program into equivalence classes based on the behavior of the program. The idea is to group inputs that should be processed in the same way by the program.

For the function binarySearch, we can divide the input domain into the following equivalence classes:

v is not present in the array a (result should be -1) v is present in the array a, and appears only once v is present in the array a, and appears more than once v is the first element of the array a v is the last element of the array a v is in the middle of the array a a has only one element, which is v a is empty Boundary Value Analysis:

Boundary value analysis is another black-box testing technique that focuses on the edges of the input domain. The idea is to test the program with inputs that are at or near the edges of the input domain, since these inputs are more likely to expose errors in the program.

For the function binarySearch, we can test the following boundary cases:

v is not present in the array a (result should be -1) v is present in the array a, and appears only once v is present in the array a, and appears more than once v is the first element of the array a v is the last element of the array a v is in the middle of the array a v is less than the first element of the array a v is greater than the last element of the array a a has only one element, which is v a is empty Test Suite:

Equivalence Partitioning:

v is not present in the array a (result should be -1) Tester Action and Input Data Expected Outcome binarySearch(7, [1, 2, 3, 4, 5]) -1

v is present in the array a, and appears only once Tester Action and Input Data Expected Outcome binarySearch(3, [1, 2, 3, 4, 5]) 2

v is present in the array a, and appears more than once Tester Action and Input Data Expected Outcome binarySearch(3, [1, 2, 3, 3, 4, 5]) 2 or 3

v is the first element of the array a Tester Action and Input Data Expected Outcome binarySearch(1, [1, 2, 3, 4, 5]) 0

v is the last element of the array a Tester Action and Input Data Expected Outcome binarySearch(5, [1, 2, 3, 4, 5]) 4

v is in the middle of the array a Tester Action and Input Data Expected Outcome binarySearch(3, [1, 2, 3, 4, 5]) 2

a has only one element, which is v Tester Action and Input Data Expected Outcome binarySearch(1, [1]) 0

a is empty Tester Action and Input Data Expected Outcome binarySearch(1, []) -1

Boundary Value Analysis:

v is not present in the array a (result should be -1) Tester Action and Input Data Expected Outcome binarySearch(0, [1,

P4. The following problem has been adapted from The Art of Software Testing, by G. Myers (1979). The a function triangle takes three integer parameters that are interpreted as the lengths of the sides of a triangle. It returns whether the triangle is equilateral (three lengths equal), isosceles (two lengths equal), scalene (no lengths equal), or invalid (impossible lengths). final int EQUILATERAL = 0; final int ISOSCELES = 1; final int SCALENE = 2; final int INVALID = 3; int triangle(int a, int b, int c) { if (a >= b+c || b >= a+c || c >= a+b) return(INVALID); if (a == b && b == c) return(EQUILATERAL); if (a == b || a == c || b == c) return(ISOSCELES); return(SCALENE); }

Ans:- Equivalence Partitioning:

Valid Equilateral triangle: {a, a, a}, where a > 0 Valid Isosceles triangle: {a, b, b}, {b, a, b}, {b, b, a}, where a, b > 0 Valid Scalene triangle: {a, b, c}, where a, b, c > 0 and a != b != c != a Invalid triangle: {a, b, c}, where a, b, c > 0 and not satisfying the triangle inequality Boundary Value Analysis:

Valid Equilateral triangle: {1, 1, 1}, {200, 200, 200}, {1000, 1000, 1000} Valid Isosceles triangle: {1, 2, 2}, {2, 1, 2}, {2, 2, 1}, {200, 200, 150}, {150, 200, 200}, {200, 150, 200}, {1000, 1000, 500}, {500, 1000, 1000}, {1000, 500, 1000} Valid Scalene triangle: {2, 3, 4}, {100, 200, 300}, {999, 1000, 1001} Invalid triangle: {1, 1, 2}, {2, 1, 1}, {1, 2, 1}, {0, 1, 1}, {1, 0, 1}, {1, 1, 0}, {201, 200, 200}, {200, 201, 200}, {200, 200, 201}, {1001, 1000, 1000}, {1000, 1001, 1000}, {1000, 1000, 1001}, {200, 200, 400}, {400, 200, 200}, {200, 400, 200} Test Suite: Equivalence Partitioning:

Valid Equilateral triangle: {3, 3, 3}, {-10, -10, -10}, {999, 999, 999} Valid Isosceles triangle: {2, 2, 3}, {2, 3, 2}, {3, 2, 2}, {199, 200, 200}, {200, 199, 200}, {200, 200, 199}, {900, 1000, 1000}, {1000, 900, 1000}, {1000, 1000, 900} Valid Scalene triangle: {2, 3, 4}, {100, 200, 300}, {998, 999, 1000} Invalid triangle: {1, 1, 2}, {2, 1, 1}, {1, 2, 1}, {0, 1, 1}, {1, 0, 1}, {1, 1, 0}, {200, 200, 400}, {400, 200, 200}, {200, 400, 200} Boundary Value Analysis:

Valid Equilateral triangle: {1, 1, 1}, {200, 200, 200}, {1000, 1000, 1000} Valid Isosceles triangle: {1, 2, 2}, {2, 1, 2}, {2, 2, 1},

P5. The function prefix (String s1, String s2) returns whether or not the string s1 is a prefix of string s2 (you may assume that neither s1 nor s2 is null). public static boolean prefix(String s1, String s2) { if (s1.length() > s2.length()) { return false; } for (int i = 0; i < s1.length(); i++) { if (s1.charAt(i) != s2.charAt(i)) { return false; } } return true; }

Ans:- Equivalence Partitioning:

Inputs that belong to the same equivalence class should have the same behavior in the program. There are two possible classes for each input string: prefixes of s2 and non-prefixes of s2. Test Suite:

Prefix s1 of s2: true Not prefix of s2: false Boundary Value Analysis:

We should consider boundary cases like empty strings, s1 equals s2, s1 of length 1, and s2 of length 1. Test Suite:

s1 and s2 are both empty strings: true s1 is an empty string and s2 is not: true s1 and s2 are equal non-empty strings: true s1 is a prefix of s2: true s1 is not a prefix of s2 and both are non-empty strings: false s1 is a single character and s2 has more than one character but does not start with s1: false s2 is a single character and is not s1: false

P6. Consider again the triangle classification program (P4) with a slightly different specification: The program reads floating values from the standard input. The three values A, B, and C are interpreted as representing the lengths of the sides of a triangle. The program then prints a message to the standard output that states whether the triangle, if it can be formed, is scalene, isosceles, equilateral, or right angled. Determine the following for the above program: a) Identify the equivalence classes for the system b) Identify test cases to cover the identified equivalence classes. Also, explicitly mention which test case would cover which equivalence class. (Hint: you must need to be ensure that the identified set of test cases cover all identified equivalence classes) c) For the boundary condition A + B > C case (scalene triangle), identify test cases to verify the boundary. d) For the boundary condition A = C case (isosceles triangle), identify test cases to verify the boundary. e) For the boundary condition A = B = C case (equilateral triangle), identify test cases to verify the boundary. f) For the boundary condition A 2 + B2 = C2 case (right-angle triangle), identify test cases to verify the boundary. g) For the non-triangle case, identify test cases to explore the boundary. h) For non-positive input, identify test points.

Ans :- a) Equivalence classes:

Invalid triangle (sum of two sides is less than or equal to the third side) Scalene triangle (all sides have different lengths) Isosceles triangle (two sides have the same length) Equilateral triangle (all three sides have the same length) Right-angled triangle (satisfies the Pythagorean theorem) b) Test cases:

Invalid triangle: {A=1, B=2, C=4} Scalene triangle: {A=3, B=4, C=5} Isosceles triangle: {A=4, B=4, C=5} Equilateral triangle: {A=6, B=6, C=6} Right-angled triangle: {A=3, B=4, C=5} c) Boundary test case for A+B=C: {A=1, B=2, C=3} d) Boundary test case for A=C: {A=3, B=4, C=3} e) Boundary test case for A=B=C: {A=5, B=5, C=5} f) Boundary test case for A^2 + B^2 = C^2: {A=3, B=4, C=5} g) Boundary test case for non-triangle: {A=1, B=2, C=5} h) Test cases for non-positive input: {A=-1, B=2, C=3}, {A=1, B=-2, C=3}, {A=1, B=2, C=-3}, {A=-1, B=-2, C=-3}

Note: Test case 1 covers equivalence class 1, test case 2 covers equivalence class 2, test case 3 covers equivalence class 3, test case 4 covers equivalence class 4, and test case 5 covers equivalence class 5. Section B:

The code below is part of a method in the ConvexHull class in the VMAP system. The following is a small fragment of a method in the ConvexHull class. For the purposes of this exercise you do not need to know the intended function of the method. The parameter p is a Vector of Point objects, p.size() is the size of the vector p, (p.get(i)).x is the x component of the i th point appearing in p, similarly for (p.get(i)).y. This exercise is concerned with structural testing of code and so the focus is on creating test sets that satisfy some particular coverage criterion. For the given code fragment you should carry out the following activities.

Convert the Java code comprising the beginning of the doGraham method into a control flow graph (CFG)
Here is the control flow graph (CFG) for the given code fragment:

sql Copy code +-----------+ | Start | +-----------+ | V +----(p.size() > 0)----+ | true | +-----------+---------+ | V +-------(1)-------+ | int i = 0; | +-------+---------+ | V +----(i < p.size())-----+ | true | +-----------+----------+ | V +-------(2)-------+ | Point p_i = p.get(i); | +-------+---------+ | V +----(hull.size() < 2)----+ | true | +-----------+-------------+ | V +----(3)----+ | hull.add(p_i); | +-------------+ | V +--------+ | i++ | +--------+ | V +----(i >= p.size())----+ | true | +-----------+----------+ | V +---(4)---+ | ... | +---------+ Note: In the above CFG, (1), (2), (3), and (4) are labeled nodes representing specific lines of code within the given code fragment.

Construct test sets for your flow graph that are adequate for the following criteria: a. Statement Coverage. b. Branch Coverage. c. Basic Condition Coverage.
Ans :- a. For Statement Coverage, we need to design test cases that execute each statement at least once. Based on the control flow graph, the following test set provides complete statement coverage:

Test set: {p=[(0,0), (0,1), (1,1), (1,0)], n=p.size()}

Test case 1: n=0 Test case 2: n=1 Test case 3: n=2 Test case 4: n=3 Test case 5: n=4

b. For Branch Coverage, we need to design test cases that execute each branch at least once. Based on the control flow graph, the following test set provides complete branch coverage: Test set: {p=[(0,0), (0,1), (1,1), (1,0)], n=p.size()}

Test case 1: n=0 Test case 2: n=1 Test case 3: n=2 Test case 4: n=3 Test case 5: n=4

c. For Basic Condition Coverage, we need to design test cases that evaluate each basic condition in both true and false outcomes. Based on the control flow graph, the following test set provides complete basic condition coverage:

Test set: {p=[(0,0), (0,1), (1,1), (1,0)], n=p.size()}

Test case 1: n=0 Test case 2: n=1 Test case 3: n=2 Test case 4: n=3 Test case 5: n=4 Test case 6: n=-1 Test case 7: n=5

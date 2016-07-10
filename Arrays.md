<h1>Java - Arrays</h1>

An array is a container object that holds a fixed number of values of a single type. The length of an array is established when the array is created. After creation, its length is fixed.
The first element of array start with zero.
 
Using an array in your program is a 3 step process:
Declaring you array.
Constructing your array.
Initializing your array.
 
<h5>Declaring Array:-
Syntax:</h5>


```
elementType[] arrayName;
Or
elementType arrayName[];
```

 
<h6>Example:</h6>

```java
int[] intArray;
int intArray[];
```
 
<h5>Constructing Array:-
Syntax:</h5>

```java
new  elementType[size];
```
 
<h6>Example:</h6>

```java
int[] intArray = new int[10]; // Defines that intArray will store 10 integer values
int intArray[] = new int[10];
```
 
<h5>Initializing Array:-
Syntax:</h5>

```java
arrayName[element 0,1,2?.. N] = value;
```
 
<h6>Example:</h6>

```java
intArray[0] = 10; // Assign an integer value 10 to the first element 0 of the array
intArray[1] = 20;
```

 
<h5>Declaring and Initializing Array:-
Syntax:</h5>

```java
elementType[] arrayName = {values1,values2,? valueN};
```
 
<h6>Example:</h6>

```java
int[] intArray = {1,2,3,4};
```
 
<h5>Array Example:</h5>

```java
public class Main {
  public static void main(String[] args) {
   
    String[] names = new String[3];
    names[0] = "A";
    names[1] = "ABC";
    names[2] = "XYZ";
    for (int i = 0; i  names.length; i++) {
      System.out.println(names[i]);
    }
    //this line should throw an exception
    //System.out.println(names[6]);
  }
}
```
```
Array are passed by refrence:
```

<h6>Arrays are passed to functions by reference, or as a pointer to the original. This means anything you do to the Array inside the function affects the original.
</h6>

<h5>Example:</h5>

```java
public class Main{
	public static void passByRefrence(String a[]){
		a[0] = "Z";
	}
	public static void main(String args[]){
		String[] b = {"A","B","C"};
		System.out.println("Before Function call  :  "+b[0]);
		Main.passByRefrence(b);
		System.out.println("After Function call : "+b[0]);
	}
}
```

Output:
Before Function call : A
After Function call : Z

 ```
Multidimensional Arrays:
```

Multidimensional arrays, are arrays of arrays.
Syntax:

```
elementType[][] arrayName = new elementType[size][size];
```
<h5>Example:</h5>

```java

int[][] intArrays = new int[4][5];
```
 
When you allocate memory for a multidimensional array, you need only specify the memory for the first (leftmost) dimension.
You can allocate the remaining dimensions separately.
In Java the length of each array in a multidimensional array is under your control.

<h5>Example:</h5>

```java
int multi[][] = new int[2][];
multi[0] = new int[5];
multi[1] = new int[4];
```
 
<h6>Array of Objects:</h6>

It is possible to create array of objects of user created class.

<h5>Example:</h5>

```java
class Employee{
	int id;
	String name;
	public void setData(int id, String name){
		this.id = id;
		this.name = name;
	}
	public void displayData(){
		System.out.println("Employee ID : "+this.id);
		System.out.println("Employee Name : "+this.name);
	}
}
class Main{
	public static void main(String args[]){
		Employee[] emp = new Employee[2];
		emp[0].setData(1,"ABC");
		emp[1].setData(2,"XYZ");
		emp[0].displayData();
		emp[1].displayData();
	}
}
```


Output:
Employee ID : 1
Employee Name : ABC
Employee ID : 2
Employee Name : XYZ
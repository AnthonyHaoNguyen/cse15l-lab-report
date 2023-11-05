# Lab Report 3
## Part 1


I choose to use the reversed method as the bug to use from week's 4 lab.
 ``` 
  // A failure-inducing input for the buggy program
  @Test
  public void testReversed1() {
    int[] input1 = {1,2,3};
    assertArrayEquals(new int[]{3,2,1}, ArrayExamples.reversed(input1));
  }

  // An input that doesn’t induce a failure
  @Test
  public void testReversed2() {
    int[] input1 = {0,0,0};
    assertArrayEquals(new int[]{0,0,0}, ArrayExamples.reversed(input1));
  }
 ``` 
![Image](Arrtest.png)


```
// Before
static int[] reversed(int[] arr) {
 int[] newArray = new int[arr.length];
 for(int i=0; i<arr.length; i+=1) {
  arr[i] = newArray[arr.length -i -1];
 }
 return arr;
}

// After
static int[] reversed(int[] arr) {
 int[] newArray = new int[arr.length];
 for(int i=0; i<arr.length; i+=1) {
  newArray[i] = arr[arr.length -i -1];
 }
 return newArray;
}
```


The goal of the code is to return a new array, so the first thing is that the before code returns the original array and not the new one. Then their code takes the elements of the new empty array and edits the original array which makes the whole array end with zeros for each element. So, the changes returns the new array and edits the new array with elements from the original array.


## Part 2


For the find command you can use; -name, -type, -mtime, and -user and for this I used the notes from the lecture presentation. When you use the command "man find" you can find the information about find that states, "the find utility shall recursively descend the directory hierarchy from each file specified by path."

```
// -name searches for files and directories that matches the "name" that we are looking for. It's useful for finding the path of a certain file/ directory name.
$ find . -name "chapter-1"
./911report/chapter-1.txt

$ find . -name plos
./plos

// -type returns all the files -f or diectories -d. It's useful for searching for files or directories when you have a lot to look through. 
$ find . -type d
.
./911report
./biomed
./government
./government/About_LSC
./government/Alcohol_Problems
./government/Env_Prot_Agen
./government/Gen_Account_Office
./government/Media
./government/Post_Rate_Comm
./plos

$ find ./government/Alcohol_Problems/ -type f
./government/Alcohol_Problems/DraftRecom-PDF.txt
./government/Alcohol_Problems/Session2-PDF.txt
./government/Alcohol_Problems/Session3-PDF.txt
./government/Alcohol_Problems/Session4-PDF.txt

// -mtime returns the files or directories that were modified in a given time. It's useful for finding the most recent file/directory edited. 
$ find ./government/Alcohol_Problems/ -mtime -3
./government/Alcohol_Problems/
./government/Alcohol_Problems/DraftRecom-PDF.txt
./government/Alcohol_Problems/Session2-PDF.txt
./government/Alcohol_Problems/Session3-PDF.txt
./government/Alcohol_Problems/Session4-PDF.txt

$ find ./government/ -mtime -1 -type d
./government/
./government/About_LSC
./government/Alcohol_Problems
./government/Env_Prot_Agen
./government/Gen_Account_Office
./government/Media
./government/Post_Rate_Comm

// -user returns the file and directoies that were created by that user. It's useful for finding file and directory made by other users or yourself when working with others.
$ find . -user Anthony
find: ‘Anthony’ is not the name of a known user

$ find ./911report/ -user Hao
./911report/
./911report/chapter-1.txt
./911report/chapter-10.txt
./911report/chapter-11.txt
./911report/chapter-12.txt
./911report/chapter-13.1.txt
./911report/chapter-13.2.txt
./911report/chapter-13.3.txt
./911report/chapter-13.4.txt
./911report/chapter-13.5.txt
./911report/chapter-2.txt
./911report/chapter-3.txt
./911report/chapter-5.txt
./911report/chapter-6.txt
./911report/chapter-7.txt
./911report/chapter-8.txt
./911report/chapter-9.txt
./911report/preface.txt
```

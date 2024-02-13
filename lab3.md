David Brin
A17749909

Hello and *welcome* to the third Lab Report!

# Part 1 - Bugs


### Failure inducing input:
```
@Test 
public void testReverseInPlace() {
    int[] input1 = { 1, 2, 3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3, 2, 1 }, input1);
}
```
### Input that does not induce a failure:

```
@Test 
public void testReverseInPlace() {
    int[] input1 = { 2};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 2}, input1);
}

```

### Symptom: failure, no failure

<img width="468" alt="image" src="https://github.com/DavidBrin/cse15l-lab-reports/assets/79377443/025ba196-32d1-451e-a020-f1a2e50eba2b">


<img width="442" alt="image" src="https://github.com/DavidBrin/cse15l-lab-reports/assets/79377443/96c3d2d9-b818-4ffa-a430-ac0f4907ba6e">

### Bug, before and after:
before:
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
After:
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length /2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
```


The new code fixes the issue because it saves the positions of the original array instead of writing over them before assigning them to the new values. 

# Part 2

researching command line prompts
## The Find Command:

#### -name
```
david@Dave MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ find ./technical/ -name Testimony_*.txt
./technical/government/Gen_Account_Office/Testimony_cg00010t.txt
./technical/government/Gen_Account_Office/Testimony_d01609t.txt
./technical/government/Gen_Account_Office/Testimony_Jul15-2002_d02940t.txt
./technical/government/Gen_Account_Office/Testimony_Jul17-2002_d02957t.txt

```
The command finds all files in the technical directory with the pattern Testimone_*.txt. Useful to find specific files by name.
```
david@Dave MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ find ./technical/ -name Legal*.txt
./technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
./technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
./technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
./technical/government/Media/Legal-aid_chief.txt
./technical/government/Media/Legal_Aid_attorney.txt
./technical/government/Media/Legal_Aid_campaign.txt
./technical/government/Media/Legal_Aid_in_Clay_County.txt
./technical/government/Media/Legal_Aid_looks_to_legislators.txt
./technical/government/Media/Legal_Aid_Society.txt
./technical/government/Media/Legal_hotline.txt
./technical/government/Media/Legal_services_for_poor.txt
./technical/government/Media/Legal_system_fails_poor.txt

```
The command finds all files in the technical directory with the pattern Legal*.txt. Useful to find specific files by name.
  
#### -type  
```
$ find ./technical/ -type d
./technical/
./technical/911report
./technical/biomed
./technical/government
./technical/government/About_LSC
./technical/government/Alcohol_Problems
./technical/government/Env_Prot_Agen
./technical/government/Gen_Account_Office
./technical/government/Media
./technical/government/Post_Rate_Comm
./technical/plos
```
the command finds all directories within the technical directory. Useful to see all folders and data storage. 
```

david@Dave MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ find ./technical/government/Alcohol_Problems -type f
./technical/government/Alcohol_Problems/DraftRecom-PDF.txt
./technical/government/Alcohol_Problems/Session2-PDF.txt
./technical/government/Alcohol_Problems/Session3-PDF.txt
./technical/government/Alcohol_Problems/Session4-PDF.txt

```
The command finds all files within the directory. Useful to see how many files are in a directory and print the names. 
#### -mtime
```
david@Dave MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ find ./technical/ -mtime -1
./technical/government/Gen_Account_Office/ai00134.txt
./technical/government/Gen_Account_Office/d01376g.txt
./technical/government/Gen_Account_Office/d03273g.txt

```
Finds all files that have been edited within the -number of days. 
```

david@Dave MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ find ./technical/ -mtime -.5
./technical/government/Gen_Account_Office/ai00134.txt
./technical/government/Gen_Account_Office/d01376g.txt
./technical/government/Gen_Account_Office/d03273g.txt

david@Dave MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ find ./technical/plos/ -mtime -.5


```
The command can also be more precise and find edited files in the directory within a fraction of a day. If no files have been edited within the time frame in the specified directory, nothing is printed.   
#### -size
```
david@Dave MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)      
$ find ./technical/ -size -1k
./technical/
./technical/911report
./technical/biomed
./technical/government
./technical/government/About_LSC
./technical/government/Alcohol_Problems
./technical/government/Env_Prot_Agen
./technical/government/Gen_Account_Office
./technical/government/Media
./technical/government/Post_Rate_Comm
./technical/plos
```
Finds all files under 1 kilobyte of data, useful for finding small files, places with room or efficiency. 
```

david@Dave MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)      
$ find ./technical/ -size +91k
./technical/911report/chapter-1.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-5.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-9.txt
./technical/biomed/1471-2105-3-2.txt
./technical/government/About_LSC/commission_report.txt
./technical/government/About_LSC/State_Planning_Report.txt
./technical/government/Alcohol_Problems/Session3-PDF.txt
./technical/government/Env_Prot_Agen/bill.txt
./technical/government/Env_Prot_Agen/ctm4-10.txt
./technical/government/Env_Prot_Agen/multi102902.txt
./technical/government/Env_Prot_Agen/tech_adden.txt
./technical/government/Gen_Account_Office/ai00134.txt
./technical/government/Gen_Account_Office/ai9868.txt
./technical/government/Gen_Account_Office/d01376g.txt
./technical/government/Gen_Account_Office/d01591sp.txt
./technical/government/Gen_Account_Office/d0269g.txt
./technical/government/Gen_Account_Office/d02701.txt
./technical/government/Gen_Account_Office/gg96118.txt
./technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./technical/government/Gen_Account_Office/im814.txt
./technical/government/Gen_Account_Office/May1998_ai98068.txt        
./technical/government/Gen_Account_Office/pe1019.txt
./technical/government/Gen_Account_Office/Sept27-2002_d02966.txt     
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
./technical/government/Gen_Account_Office/Testimony_cg00010t.txt     
```
Finds all files above 91 kilobytes, useful for identifying large files, files that may slow down the program.  
# Works Cited
  
### **ChatGPT:**      
##### Prompt:  
"What are 4 different ways or options to use find in the command line?"  
######  Output: 
"The `find` command in the command line is a powerful tool for searching for files and directories based on various criteria. Here are four different ways/options to use the `find` command:

1. **Search by Name:**
   You can use the `find` command to search for files or directories by their names.
   ```
   find /path/to/search -name "filename"
   ```

2. **Search by Type:**
   You can search for files based on their types, such as regular files, directories, symbolic links, etc.
   ```
   find /path/to/search -type f
   ```

3. **Search by Modification Time:**
   You can search for files based on their modification time. For example, to find files modified in the last 24 hours:
   ```
   find /path/to/search -mtime -1
   ```

4. **Search by Size:**
   You can search for files based on their size. For example, to find files greater than 10MB:
   ```
   find /path/to/search -size +10M
   ```

These are just a few examples of how you can use the `find` command. It offers many more options for customizing your searches, including searching by permissions, owner, and more. You can explore additional options and combinations by referring to the `find` command's manual (`man find`) or online documentation."

# Welcome to Lab 5!


***Edstem Conversation About Debugging***

### Student Question

I ran this grader shell script and I'm getting an error. I'm not sure why it's not working but the error message it prints out says the error is in the ListExamples.java file and that there is a semi colon missing but I have a semicolon. 

  Here is the error message:  
  
  <img width="678" alt="image" src="https://github.com/DavidBrin/cse15l-lab-reports/assets/79377443/a5a71540-33ee-44f0-a004-c529b04f1265">
  
  Here is the code:    
  <img width="503" alt="image" src="https://github.com/DavidBrin/cse15l-lab-reports/assets/79377443/4d0b7650-e47c-481d-9587-45a3d156bda0">


### TA Response

The semicolon is a suggestion when the compiler sees an incomplete line and it may be misleading because it often pops up from other errors. Look at like 17, where the compiler found the error and read through your declarations and assignments to look for anything out of place or characters accidentally added. 
  
  

### Student Response

  Thanks so much for your help, I looked through the code, keeping what you said in mind and found an "S" in line 17 where it wasn't supposed to be. I deleted the bug and reran the code. 

  Here is the updated, debugged code:   
<img width="447" alt="image" src="https://github.com/DavidBrin/cse15l-lab-reports/assets/79377443/aa9b3994-a2be-43ea-8ff2-8431f7e09a31">

Here is the working grade message, bug fixed:  
<img width="757" alt="image" src="https://github.com/DavidBrin/cse15l-lab-reports/assets/79377443/fa75c5f9-df70-4869-9466-a1e7e8a0e516">


### Setup

- Files: TestListExamples.java grade.sh
- Directory Structure: <img width="133" alt="image" src="https://github.com/DavidBrin/cse15l-lab-reports/assets/79377443/aa05c357-d4b0-4bcf-be0b-1e4719a36ed0">
- Here is the code before:  
  <img width="503" alt="image" src="https://github.com/DavidBrin/cse15l-lab-reports/assets/79377443/4d0b7650-e47c-481d-9587-45a3d156bda0">
- Command line args ` bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected`

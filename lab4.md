# Lab 4: Vim

Tasks:

- Log into ieng6
- Clone your fork of the repository from your Github account (using the SSH URL)
- Run the tests, demonstrating that they fail
- Edit the code file to fix the failing test
- Run the tests, demonstrating that they now succeed
- Commit and push the resulting change to your Github account (you can pick any commit message!)

### Log into ieng6

<img width="494" alt="image" src="https://github.com/DavidBrin/cse15l-lab-reports/assets/79377443/8ada9e71-e8fc-4fcf-839a-076b366e8170">

I typed `ssh` and my account for remote access

### Clone the fork of the repository from GitHub

<img width="473" alt="image" src="https://github.com/DavidBrin/cse15l-lab-reports/assets/79377443/080f19a5-c0a7-4fde-b000-c0335900cb8c">

To clone the repository from GitHub, I typed `git clone` and `<CTRL>-V` because the SSH link was copied to my clipboard. I typed `ls` in the picture just to demonstrate I was in the right repository because it was already cloned. 

### Running tests and showing failures

<img width="443" alt="image" src="https://github.com/DavidBrin/cse15l-lab-reports/assets/79377443/4fc0ba09-aae8-4779-8f91-116de7403a6f">

Keys pressed: `<up><up><up><up><enter>`, `<up><up><up><up><enter> `
The `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java `
command was 4 up in the search history, so I used up arrow to access it. 
Then the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore 
ListExamplesTests` command was 4 up in the history, so I accessed and ran it in the same way.

### Edit the code file to fix the test

<img width="494" alt="image" src="https://github.com/DavidBrin/cse15l-lab-reports/assets/79377443/a8adb4ce-84a3-492c-a26c-3069bcb3bc19">

Keys pressed: `vim ListExamplesTests.java <enter>` which took me to the editor where I could press `<down>` until I got to the right line and use `6w` to get to the problem word and `a` to edit and replace the problem. 
Finally, `:wq <enter>` to exit and save the file. 

### Running tests with success

<img width="592" alt="image" src="https://github.com/DavidBrin/cse15l-lab-reports/assets/79377443/bdb3912a-8c2e-44be-a2ca-dd4382b291fc">

Keys pressed: `<up><up><up><up><enter>`, `<up><up><up><up><enter> `
The `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java `
command was 4 up in the search history, so I used up arrow to access it. 
Then the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore 
ListExamplesTests` command was 4 up in the history, so I accessed and ran it in the same way.

### Commit and push to GitHub

<img width="485" alt="image" src="https://github.com/DavidBrin/cse15l-lab-reports/assets/79377443/aa6bbbb8-6c32-4928-b033-3222e96409c6">

Finally, I committed and pushed changes to GitHub by typing `git add Li<Tab> .java<enter>` and 
`git commit -m wasgood <enter>` to commit and send a message and `git push origin main` to push changes back to account.

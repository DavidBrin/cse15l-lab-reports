David Brin
A17749909

Hello and *welcome* to the third Lab Report!

# Part 1 - Bugs

Provide:

- A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
- An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
- The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
- The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
Briefly describe why the fix addresses the issue.

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

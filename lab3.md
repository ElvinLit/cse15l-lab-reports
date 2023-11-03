# Lab Report 3

## Part 1 - Bugs
Choose one of the bugs from week 4’s lab.

Provide:
- A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
`@Test
public void testReversed2() {
  int[] input1 = {1,2,3,4,5};
  assertArrayEquals(new int[]{5,4,3,2,1}, ArrayExamples.reversed(input1));
}`
- An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
- The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
- The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
- Briefly describe why the fix addresses the issue.
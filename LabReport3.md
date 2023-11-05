# Lab Report 3
## Part 1


I choose to use the reversed method as the bug to use from week's 4 lab.
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

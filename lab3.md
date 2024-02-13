# Lab Report 3

## Part 1
1. A *failure-inducing* input
```
    int[] intArray = {1, 2, 3, 4, 5};

    @Test
    public void testFailureInducingReversedMethod() {

        int[] newIntArray = ArrayExamples.reversed(intArray);
        assertEquals("New array should not have this value at index 0", 
            0, newIntArray[0]);
        assertEquals("New array should not have this value at index 1", 
            0, newIntArray[1]);    
        assertEquals("New array should not have this value at index 2", 
            0, newIntArray[2]);
        assertEquals("New array should not have this value at index 3", 
            0, newIntArray[3]);
        assertEquals("New array should not have this value at index 4", 
            0, newIntArray[4]);
        assertArrayEquals("Array shouldn't compose of these numbers", 
            new int[] {0, 0, 0, 0, 0}, newIntArray);
        
    }
```

2. An input that *doesn't* induce a failure
```
    @Test
    public void testReversedMethod() {

        int[] newIntArray = ArrayExamples.reversed(intArray);
        assertEquals("New array should have correct length", 
            5, newIntArray.length);
        assertEquals("New array should be in reversed order", 
            new int[] {5, 4, 3, 2, 1}, newIntArray);
        assertEquals("Int at index 0 should be 5", 5, newIntArray[0]);
        assertEquals("Int at index 1 should be 4", 4, newIntArray[1]);
        assertEquals("Int at index 2 should be 3", 3, newIntArray[2]);
        assertEquals("Int at index 3 should be 2", 2, newIntArray[3]);
        assertEquals("Int at index 4 should be 1", 1, newIntArray[4]);

    }
```

3. The Symptoms
> Screenshot of the failure-inducing input test 
> <img width="705" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/bfe29378-3dfe-48b6-9f66-70c8f554995c">

> Screenshot of the regular input test
> <img width="851" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/fbdfcd19-82d7-4ca8-99c1-e0a1f069595e">

4. The Bug Located in the File
> Before
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

> After
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }

    return newArray;
  }
```

## Part 2
**The `less` Command**

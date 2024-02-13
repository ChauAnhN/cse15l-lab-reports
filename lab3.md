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
            new Integer[] {5, 4, 3, 2, 1}, newIntArray);
        assertEquals("Int at index 0 should be 5", 5, newIntArray[0]);
        assertEquals("Int at index 1 should be 4", 4, newIntArray[1]);
        assertEquals("Int at index 2 should be 3", 3, newIntArray[2]);
        assertEquals("Int at index 3 should be 2", 2, newIntArray[3]);
        assertEquals("Int at index 4 should be 1", 1, newIntArray[1]);

    }
```

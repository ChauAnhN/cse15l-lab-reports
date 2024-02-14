# Lab Report 3

## Part 1
**Choosen Bug:** ArrayExamples.java

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
1. Previewing files (Source: ChatGPT)
> Example 1: Using it on a text file in `./technical/biomed`.

**INPUT:**
```
less 1471-213X-1-4.txt
```

**OUTPUT:**
```
        Background
        The Cre-
        loxP site specific recombination
        system [ 1] is widely used for production of
        tissue-specific and conditional knockout alleles in mice [
        2, 3]. Recently, a Cre-dependent
        lacZ reporter strain (R26R) was
        produced by targeted insertion of a lacZ gene, preceded by
        a loxP-flanked (floxed) strong transcriptional termination
        sequence (tpA), into the ubiquitously expressed ROSA26
        . . .
```

As shown above, it prints out the contents of the text file in the terminal up to the length of the panel. This is useful because it allows us to view the file contents without having to look for it manually, especially if we have a large folder with many files.

> Example 2: Using it on a text file in `./technical/government/About_LSC`.

**INPUT:**
```
less diversity_priorities.txt
```

**OUTPUT:**
```
        (held May 31 and June 1 in Washington. D.C.)




        OVERVIEW
        On May 31 and June 1, 2001, approximately fifty equal justice
        advocates gathered in Washington, DC for LSC's and NLADA's first
        national conference on diversity in the legal services community.
        . . .
```

As shown above, this command prints out the contents of the text file, including the blank line spaces, in the terminal. This is useful because it allows us to view the file contents without having to continually scroll through a file with large files and sub-files.

2. Printing out the contents of a specific line from a file (Source: [I/O Flood Article](https://ioflood.com/blog/less-linux-command/))
> Example 1: Using it on a text file in `./technical/biomed`.

**INPUT:**
```
less 1471-213X-1-4.txt
g50
```

**OUTPUT**
```
        a stop sequence, and in one of these, lacZ is expressed
        prior to the Cre-mediated excision event. In the third
        strain, which is similar in principle to the YFP and CFP
        alleles reported here, EGFP was inserted at the
        ROSA26 locus [ 20]. The availability
        of different Cre reporter strains will be valuable, not
        only because of the advantages of different reporter
        proteins, but also because the efficiency of Cre-mediated
        excision may be dependent on the target locus.


        Results and Discussion
        . . .
```

As shown above, the command makes the terminal skip 50 lines in the file and prints out the contents on the next line after skipping the previous ones. This is useful because it makes it easier to search through the file content faster compared to simply using the `enter` button, which just prints line by line.

> Example 2: Using it on a text file in `./technical/government/About_LSC`.

**INPUT:**
```
less diversity_priorities.txt
g50
```

**OUTPUT:**
```
        internally and externally.


        •
        Identify obstacles within our legal services community
        that cause and/or perpetuate bias, oppression, and
        unfairness.


        •
        Brainstorm strategies to address the identified issues,
        overcome the challenges and obstacles, and to promote justice,
        . . .
```

As illustrated by the code blocks, the command makes the terminal skip to the 50th line in the file and prints out the next line's contents. This is useful because it allows the user to look through the contents of the files faster.

3. Searching for a specific word in a text file (Source: [Linux Handbook Article](https://linuxhandbook.com/less-command/)) 
> Example 1: Using it on a text file in `./technical/biomed`.

**INPUT:**
```
less 1471-213X-1-4.txt
/background
```

**OUTPUT:**
```
...skipping...
        No **background** expression of EYFP or ECFP could be
        detected in the R26R-EYFP or R26R-ECFP mice, as expected
        (data not shown), due to the strong transcriptional stop
        sequence inserted between the promoter and the coding
        sequences. However, when the reporter mice were crossed to
```

As displayed above, the command `less`, followed by a `/` and the word of interest, helps search for paragraphs within the text file that contain that specific word of interest. This is useful for finding important words, paragraphs, or sections in a file without having to read through the whole file manually.

> Example 2: Using it on a text file in `./technical/government/About_LSC`.

**INPUT:**
```
less diversity_priorities.txt
/diversity
```

**OUTPUT:**
```
        ...skipping...
        national conference on **diversity** in the legal services community.
        Focusing on broad aspects of **diversity** - including, among others,
        age, gender, disability, sexual orientation, race, ethnicity and
        national origin - participants examined **diversity**-related strengths
        and challenges facing clients, staff and program leaders (both
        local and national), and brainstormed about potential strategies
        for addressing the challenges. To ensure that the dialogue would
        include the variety of issues and individuals in the legal services
        community, NLADA and LSC selected participants to reflect both the
        leadership and emerging leadership of the field. To the maximum
        extent possible, participants broadly mirrored the full population
        of the national community. Attendance at the meeting was limited to
        about 50 people to foster candid conversation. Two members of the
        Karp Consulting Group (Deborah Howard and Yvonne Shinhoster Lamb)
        facilitated the two-day session.
```

As shown in the code blocks, the command `less`, followed by a `/` and the specific word, helps search for sections in a file that contain the specified word. This helps reduce the time it takes to search for key sections and phrases within a text file.

4. Marking intieresting points in a file (Source: [Linux Handbook Article](https://linuxhandbook.com/less-command/))
> Example 1: Using it on a text file in `./technical/biomed`.

**INPUT:**
```
less 1471-213X-1-4.txt
ma
```

**OUTPUT:**
```
        Here, we describe the production of two similar Cre
        reporter alleles that express enhanced yellow or cyan
set mark:
```

As shown above, the command `m` followed by a letter (in this example, `a`) of the user's choice allows the user to bookmark an interesting section in the text file. Later on, when the user enters the following input `'` followed by the letter they chose . . .
```
'a
```

. . . they will receive the paragraph they marked as the following output:
```
        targeted ES cells, originally derived from strain 129X1/SvJ
goto mark:
        . . .
        Here, we describe the production of two similar Cre
        reporter alleles that express enhanced yellow or cyan
```
This is useful because it helps users go back to sections of interest in a text file without spending extra time scrolling through and re-reading the file.

> Example 2: Using it on a text file in `./technical/government/About_LSC`.

**INPUT:**
```
less diversity_priorities.txt
mb
```

**OUTPUT:**
```
        All participants understood that, while the assembled group
        reflected the demographics of the community, they did not speak for
        every member of the broad-based legal services community. It should
        be noted also that no clients were involved in this event. Thus the
set mark:
```
As shown above, the command `m` followed by a simple letter (in this example, `b`) marks a section of interest in the text file. Later on, when the user enters the following input `'` followed by the letter they chose . . .

```
'b
```

. . . they will be brought back to the paragraph they marked, similar to the previous example.
```
    •
    Today's key constituents include governing and policy
    boards and clients (those being served and those not being served).
goto mark:
    . . .
    All participants understood that, while the assembled group
    reflected the demographics of the community, they did not speak for
    every member of the broad-based legal services community. It should
    be noted also that no clients were involved in this event. Thus the
```
This is useful because it allows users to go back to sections in a file they found interesting without having to spend time looking through the file again.




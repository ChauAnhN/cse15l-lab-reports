# Lab 5 Report

> Student: Hello! I'm lost as to how to fix my code, and I can't seem to pinpoint it after looking through my code. Below is my code and test cases. My directory is the `lab7` folder.

**CODE:**

```
import java.util.ArrayList;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0, s);
      }
    }
    return result;
  }


  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index1 += 1;
    }
    return result;
  }


}
```

```
import static org.junit.Assert.*;
import org.junit.*;
import java.util.*;
import java.util.ArrayList;


public class ListExamplesTests {
	@Test(timeout = 500)
	public void testMerge1() {
    		List<String> l1 = new ArrayList<String>(Arrays.asList("x", "y"));
		List<String> l2 = new ArrayList<String>(Arrays.asList("a", "b"));
		assertArrayEquals(new String[]{"x", "y", "a", "b"}, ListExamples.merge(l1, l2).toArray());
	}
	
	@Test(timeout = 500)
        public void testMerge2() {
		List<String> l1 = new ArrayList<String>(Arrays.asList("a", "b", "c"));
		List<String> l2 = new ArrayList<String>(Arrays.asList("c", "d", "e"));
		assertArrayEquals(new String[]{ "a", "b", "c", "c", "d", "e" }, ListExamples.merge(l1, l2).toArray());
        }

}
```

**OUTPUT:**

```
[rm092@ieng6-201]:lab7:208$ bash test.sh
  ...
There were 2 failures:
1) testMerge1(ListExamplesTests)
arrays first differed at element [0]; expected:<[x]> but was:<[a]>
  ...
2) testMerge2(ListExamplesTests)
java.lang.OutOfMemoryError: Java heap space
  ...

FAILURES!!!
Tests run: 2,  Failures: 2
```

---

> Educational Staff: Hmm, look over your test case for your tester file. Are the outputs you're testing for the correct expected values?

---

> Student: Oh, it turns out the first test case in my tester file was incorrect. I had the first list `l1` and `l2` in the opposite expected order. Instead of the expected output being `{"x", "y", "a", "b"}`, it should've been `{"a", "b", "x", "y}`. I'm passing the first test now. However, my code is still failing the second test and I'm not sure why. I'm still receiving an out of memory error. Below is my new test file and output. Do you think there's something else I'm missing? I'm sure both are correct.

**CODE:**

```
	@Test(timeout = 500)
	public void testMerge1() {
    		List<String> l1 = new ArrayList<String>(Arrays.asList("x", "y"));
		List<String> l2 = new ArrayList<String>(Arrays.asList("a", "b"));
		assertArrayEquals(new String[]{"a", "b", "x", "y"}, ListExamples.merge(l1, l2).toArray());
	}
```

**OUTPUT:**

```
[rm092@ieng6-201]:lab7:208$ bash test.sh
  ...
There was 1 failure:
1) testMerge2(ListExamplesTests)
java.lang.OutOfMemoryError: Java heap space
  ...

FAILURES!!!
Tests run: 2,  Failures: 1
```

---

> Educational Staff: Run `bash test.sh` again and look at the error where the line occurred.

---

> Student: Oh, it turns out that one of my if statements was incorrect. Instead of assigning `index1 += 1` while `while(index2 < list2.size())`, I should've assigned `index2 += 1` instead. Below is my correct code! Thank you for the help.

**CODE:**

```
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      // change index1 below to index2 to fix test
      index2 += 1;
    }
    return result;
```

**OUTPUT:**

```
[rm092@ieng6-201]:lab7:208$ bash test.sh
  ...
JUnit version 4.13.2
..
Time: 0.016

OK (2 tests)
```

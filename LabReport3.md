### Lab Report 3 - Bugs and Commands (Week 5)

## Part 1 - Bugs

### Bug Description

**Chosen Bug: Week 4 - ArrayIndexOutOfBoundsException**

**Failure-Inducing Input:**

```java
import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

public class BuggyProgramTest {

    @Test
    public void testFailureInducingInput() {
        int[] input = {1, 2, 3};
        int index = 3; // Index out of bounds
        assertThrows(ArrayIndexOutOfBoundsException.class, () -> {
            int result = BuggyProgram.getElementAtIndex(input, index);
        });
    }
}
```

**Non-Failure-Inducing Input**:

```java
import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

public class BuggyProgramTest {

    @Test
    public void testNonFailureInducingInput() {
        int[] input = {1, 2, 3};
        int index = 2; // Valid index
        assertDoesNotThrow(() -> {
            int result = BuggyProgram.getElementAtIndex(input, index);
        });
    }
}
```

**Symptom:**


**Buggy Code (Before Fix):**
```java
public class BuggyProgram {
    public static int getElementAtIndex(int[] array, int index) {
        return array[index];
    }
}
```

**Fixed Code (After Fix):**
```java
public class BuggyProgram {
    public static int getElementAtIndex(int[] array, int index) {
        if (index < 0 || index >= array.length) {
            throw new ArrayIndexOutOfBoundsException("Index " + index + " is out of bounds");
        }
        return array[index];
    }
}
```
**Explanation:**
The fix addresses the issue by adding a boundary check for the index. If the index is less than 0 or greater than or equal to the length of the array, an ArrayIndexOutOfBoundsException is thrown with a descriptive message. This prevents the program from attempting to access an invalid array index and causing a runtime exception.

### 
markdown
Copy code
### Lab Report 3 - Bugs and Commands (Week 5)

## Part 1 - Bugs

### Bug Description

**Chosen Bug: Week 4 - ArrayIndexOutOfBoundsException**

**Failure-Inducing Input:**

```java
import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

public class BuggyProgramTest {

    @Test
    public void testFailureInducingInput() {
        int[] input = {1, 2, 3};
        int index = 3; // Index out of bounds
        assertThrows(ArrayIndexOutOfBoundsException.class, () -> {
            int result = BuggyProgram.getElementAtIndex(input, index);
        });
    }
}
Non-Failure-Inducing Input:

java
Copy code
import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

public class BuggyProgramTest {

    @Test
    public void testNonFailureInducingInput() {
        int[] input = {1, 2, 3};
        int index = 2; // Valid index
        assertDoesNotThrow(() -> {
            int result = BuggyProgram.getElementAtIndex(input, index);
        });
    }
}
Symptom:


Buggy Code (Before Fix):

java
Copy code
public class BuggyProgram {
    public static int getElementAtIndex(int[] array, int index) {
        return array[index];
    }
}
Fixed Code (After Fix):

java
Copy code
public class BuggyProgram {
    public static int getElementAtIndex(int[] array, int index) {
        if (index < 0 || index >= array.length) {
            throw new ArrayIndexOutOfBoundsException("Index " + index + " is out of bounds");
        }
        return array[index];
    }
}
Explanation:
The fix addresses the issue by adding a boundary check for the index. If the index is less than 0 or greater than or equal to the length of the array, an ArrayIndexOutOfBoundsException is thrown with a descriptive message. This prevents the program from attempting to access an invalid array index and causing a runtime exception.


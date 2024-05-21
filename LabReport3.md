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

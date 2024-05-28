# Lab Report 5 - Putting it All Together (Week 9)

## Part 1- Debugguing Scenario

## Original Post from Student
### Subject: [Debugging Help] Unexpected Output in Java Program

Hi everyone,

I'm having some trouble with my java program from the files searching system assignment. When I run my program, it doesn't seem to be finding any files, even though I know the files are there. Here's a screenshot of my terminal output and my code. I suspect the issue might be with how I'm reading the directories, but I'm not sure.

## Screenshot 1: Terminal Output
![Screenshot](Screenshot1.png)

## Java Code (SearchFiles.java)

```java

import java.io.File;

public class SearchFiles {
    public static void main(String[] args) {
        if (args.length < 1) {
            System.out.println("Please provide a directory to search.");
            return;
        }
        
        File dir = new File(args[0]);
        if (!dir.exists() || !dir.isDirectory()) {
            System.out.println("Directory does not exist.");
            return;
        }
        
        File[] files = dir.listFiles();
        if (files == null || files.length == 0) {
            System.out.println("No files found.");
        } else {
            for (File file : files) {
                System.out.println("Found file: " + file.getName());
            }
        }
    }
}
```
Any ideas on what might be going wrong?

## Response from TA

Hi John,

Thanks for sharing the details. It looks like your code should be listing files in the specified directory, but it's not finding any files. Could you try running the following command and share the output with us?

![Screenshot](Screenshot1.png)

This will help us verify if there are files in the directory and if there might be any permission issues.

## Follow-up Post from Student

Sure, I ran the command you suggested. Here’s the output:


## Screenshot 2: Terminal Output After Running `ls` Command

![Screenshot](Screenshot1.png)

So it looks like the files are definitely there. What could be the issue?

## Response from TA

Thanks for the output. It looks like the files are present in the directory. One possibility is that your script might not be passing the directory argument correctly to the Java program. Could you share the content of your `run_search.sh` script?

## Follow-up Post from Student
Here’s the content of my run_search.sh script:

![Screenshot](Screenshot1.png)

## Response from TA

Thanks for sharing that. The script looks correct, but to troubleshoot further, let's add some debug prints to your Java program to ensure the argument is being passed correctly. Modify your SearchFiles.java file like this:

```java
import java.io.File;

public class SearchFiles {
    public static void main(String[] args) {
        if (args.length < 1) {
            System.out.println("Please provide a directory to search.");
            return;
        }
        
        System.out.println("Searching in directory: " + args[0]);
        
        File dir = new File(args[0]);
        if (!dir.exists() || !dir.isDirectory()) {
            System.out.println("Directory does not exist.");
            return;
        }
        
        File[] files = dir.listFiles();
        if (files == null || files.length == 0) {
            System.out.println("No files found.");
        } else {
            for (File file : files) {
                System.out.println("Found file: " + file.getName());
            }
        }
    }
}
```

Run your script again and see what the output is.

## Follow-up Post from Student

I added the debug print and ran the script again. Here’s the output:

## Screenshot 3: Terminal Output After Adding Debug Print

![Screenshot](Screenshot1.png)

Looks like the directory isn’t being recognized correctly. What should I do next?

## Response from TA

Great, the debug print helped us identify the issue. It looks like there might be an extra whitespace character in your script or a typo in the directory path. Double-check that the path is correct and doesn't contain any hidden characters or typos. Try copying the path directly from your ls command output.

Additionally, let's check for any hidden characters in your script using the cat -A command:

![Screenshot](Screenshot1.png)

## Follow-up Post from Student

I ran the cat -A command, and here's the output:

## Screenshot 4: Terminal Output After Running cat -A Command




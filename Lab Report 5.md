# Lab Report 5 - Putting it All Together (Week 9)

## Part 1- Debugguing Scenario

## Original Post from Student
### Subject: [Debugging Help] Unexpected Output in Java Program

Hi everyone,

I'm having some trouble with my java program from the files searching system assignment. When I run my program, it doesn't seem to be finding any files, even though I know the files are there. Here's a screenshot of my terminal output and my code. I suspect the issue might be with how I'm reading the directories, but I'm not sure.

## Screenshot 1: Terminal Output


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

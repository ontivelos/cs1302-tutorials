# Brief Introduction to Java Threads

![Approved for: Spring 2020](https://img.shields.io/badge/Approved%20for-Spring%202020-blue)

## Prerequisites

This tutorial assumes that the reader has a knowledge of basic Unix commands and experience working with a command-line text editor (e.g. emacs, vi, etc.). Readers should also be familiar with compiling and running Java programs from the command-line. 
To get the most out of this tutorial, you should follow along and take notes.

## Course-Specific Learning Outcomes

* **LO7.a:** Design and implement a graphical user interface in a software project.

## Introduction Video

In this video, we introduce the concept of a thread and provide some code examples to illustrate how threads 
can be used to make your program execute two pieces of code at the same time. Many of the definitions presented 
in this video are simplified in order to make them more approachable for beginners.

https://youtu.be/zCeo15G3nvI

<a href="https://www.youtube.com/watch?v=zCeo15G3nvI">
<img src="https://img.youtube.com/vi/zCeo15G3nvI/0.jpg?20190726" alt="IMAGE ALT TEXT">
</a>

## JavaFX Application Thread

In this video, we briefly discuss the JavaFX Application Cycle and the JavaFX Application Thread 
and how their design might impact your code for event handlers and programmatic changes to 
the scene graph.

https://youtu.be/9qCUqzYGGpo

<a href="https://www.youtube.com/watch?v=9qCUqzYGGpo">
<img src="https://img.youtube.com/vi/9qCUqzYGGpo/0.jpg?20190726" alt="IMAGE ALT TEXT">
</a>

## Example Starter Code

Here is the example code for the first video:

```java
package cs1302.threads;

/**
 * Driver for thread example.
 */
public class ThreadDriver {

    public static void main(String[] args) {
        loop("###");
        loop("---");
        System.err.println("main thread is done.");
    } // main

    /**
     * Executes an infinite loop.
     * @param name loop name
     */
    public static void loop(String loopName) {
        int x = 0;
        while (true) {
            System.err.printf("%s-%d\n", loopName, x);
            x += 1;
        } // while
    } // loop

    /**
     * Creates and immediately starts a new daemon thread that executes
     * {@code target.run()}. This method, which may be called from any thread,
     * will return immediately its the caller.
     * @param target the object whose {@code run} method is invoked when this
     *               thread is started
     */
    public static void runNow(Runnable target) {
        Thread t = new Thread(target);
        t.setDaemon(true);
        t.start();
    } // runNow

} // ThreadDriver
```

<hr/>

[![License: CC BY-NC-ND 4.0](https://img.shields.io/badge/License-CC%20BY--NC--ND%204.0-lightgrey.svg)](http://creativecommons.org/licenses/by-nc-nd/4.0/)

<small>
Copyright &copy; Michael E. Cotterell, Brad Barnes, and the University of Georgia.
This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/">Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License</a> to students and the public.
The content and opinions expressed on this Web page do not necessarily reflect the views of nor are they endorsed by the University of Georgia or the University System of Georgia.
</small>

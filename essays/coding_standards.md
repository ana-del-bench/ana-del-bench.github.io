---
layout: essay
type: essay
title: "Clean Code Isn't Just Pretty"
# All dates must be YYYY-MM-DD format!
date: 2023-09-22
published: true
labels:
  - Coding Standards
  - Javascript
---

## Why That Green Checkmark is So Satisfying

There comes a level of satisfaction that comes with clean code. However, that’s something that tends to go out the window when faced with a time limit or when focused on a tricky problem. The issue with this is that those scenarios often rely on code that’s easy to read and look back on. This is where tools like ESLint come in handy. Having something that will consistently keep you in check is a great way to make sure that your code is formatted well as you’re typing it (as opposed to going back and having to fix everything while debugging). There is a sense of satisfaction that comes with finishing a project and seeing that green checkmark in your editor. That checkmark isn’t only indicative of pleasing aesthetics. Given that the code works, it’s also an assurance that anybody who looks at it in the future will be able to understand what you accomplished and how you did it. In my experience, enforcing coding standards like this is a great way to develop good habits that will carry onto future projects.

## No Clean Code Is The Same

With coding standards differing between environments, sometimes practices may be situation-specific but there are certain overarching standards that pretty much everyone follows. For instance, one of my past professors required very specific formatting when it came to projects. Each function had to be preceded by (truly) a paragraph detailing various aspects of each function, each indentation was to be done with exactly 5 spaces instead of a tab, etcetera. While adding notation to the extent that was required in that class may seem excessive anywhere else, it *is* a universal standard to include the proper documentation necessary to clearly convey the important aspects of any functions. The same goes for indentation, while 5 spaces isn’t exactly the norm, proper indentation in general is still a very useful habit to form along with others like efficient naming conventions or proper spacing between segments that make code appreciably cleaner and more efficient for future viewers.

In certain cases these coding standards, while not essential in one language, can become imperative for another. For instance, while Javascript doesn’t *need* a semicolon at the end of every line of code, maintaining such a habit could prove useful when transitioning to a language like Java that does require semicolons.

This Javascript code is *technically* fine:
```cpp
function helloWorld() {
    console.log(“Hello World”)
}
```

This Java code is not:
```cpp
public static void helloWorld() {
    system.out.println(“Hello World”)		//lack of semicolon will cause an error
}
```

The same thing applies to indentation, while indentation errors won’t cause any problems when using languages like Java, it very much will cause errors when using Python.

This Java code is *technically* fine:
```cpp
public static void helloWorld() {
system.out.println(“Hello World”);
}
```

This Python code is not:
```cpp
def helloWorld():
print(“Hello World”)		//improper indentation will cause an error
```

Maintaining proper formatting habits (at least where applicable) not only helps to make your overall code more consistent and easy to understand, it can also save you some debugging stress in the future.

## In Conclusion

Holding oneself accountable when it comes to proper coding standards is an extremely beneficial practice, not only for personal benefit but also for anybody who you collaborate with in the future. There are certain practices that remain universal for documentation and, even through the various workplaces you may experience with different standards, having a good foundation of coding habits has the added benefit of making it easier to adapt to these changes. The advantages are clear, and using tools like ESLint makes it even easier to maintain these standards amongst situations where proper documentation often slips to the bottom of the priority list.



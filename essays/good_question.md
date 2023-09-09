---
layout: essay
type: essay
title: "How To Be Efficiently Confused"
# All dates must be YYYY-MM-DD format!
date: 2023-09-08
published: true
labels:
  - Questions
  - Answers
  - StackOverflow
---

<img width="300px" class="rounded float-start pe-4" src="../img/smart-questions/smart_question_meme.jpg">

## Online Forums Are Intimidating

Adding your question to an online forum as massive and well-known as StackOverflow can be daunting. However, if you've decided to brave that front, there’s an article by programmers Eric S.Raymond and Rick Moen called [How To Ask Questions The Smart Way](http://www.catb.org/esr/faqs/smart-questions.html#keepcool). This article details the do’s-and-dont’s of formatting a question when seeking advice in online forums and is a very good document to reference if you're planning to seek help from the internet masses. Skills like these can determine whether or not you actually get help, and whether or not that help is actually useful to you. It’s important to know how to best help the people trying to help you. That way, the quality of the experience raises for everyone involved.

## Good Questions vs Bad Questions

When a question is unclear or poorly formatted it can lead to instances like this. The subject header of the question is [“Can anybody tell me why this is happening in c language”](https://stackoverflow.com/questions/46015068/can-anybody-tell-me-why-this-is-happening-in-c-language), with no further details about their problem or question.  As for the question itself, the viewer is provided two simple functions written in C that differ slightly from each other but generally do the exact same operation. 

This is what the functions looked like, pretty simple right?
```cpp
int main(void)
 {
     float a=10;
    printf("%f"+1,a);

    return 0;
 }
```
```cpp
 int main(void)
 {
     float a=10;
    printf("%f"+36,a);

    return 0;
 }
```

However, while the code is simple enough to understand what is happening at a glance, it’s significantly harder to determine what the inquirer was trying to do with these functions. With no other clarification about the problem other than a request for an explanation as to why the two functions have different outputs, anyone trying to help would just be taking a shot at what they think the inquirer needs help with. Which is exactly what happened. Most of the resulting answers include some form of the statement “I’m not sure what you’re trying to accomplish but…”.  As an additional consequence, the answers ended up significantly varying from each other, ranging from compiling errors to more common syntax errors. There were no follow-up responses from the inquirer, and they never accepted an answer, so their true intent remains speculative.

On the other hand, when a question is asked in a more efficient matter, those who try to help will have an easier time formatting their answer because there’s already a mutual understanding of the problem. Take this question with the subject header [“Sort ArrayList of custom Objects by property”](https://stackoverflow.com/questions/2784514/sort-arraylist-of-custom-objects-by-property). The title clearly states the objective that they need assistance with, and the question tags include further elaboration (comparator, java, sorting, date) on the issue. In this instance, the inquirer was trying to sort an array of custom Objects by their date. The description lead with their prior research on sorting arrays, as well as their subsequent attempts to find a solution through their own research. The inquirer had visibly tried to research a solution to the best of their abilities and had even made some progress on the issue but couldn't get past a certain point. They additionally made the effort to suggest possible solutions that they had thought of, but didn't know how to implement. This effort especially made it easier for the responder to provide a concise solution, filling in the gaps that the inquirer hadn't been able to fill with their research.

Inquirer's proposed solution:
```cpp
public class CustomComparator {
    public boolean compare(Object object1, Object object2) {
        return object1.getStartDate().before(object2.getStartDate());
    }
}
```

Responder's code:
```cpp
public class CustomComparator implements Comparator<MyObject> {
    @Override
    public int compare(MyObject o1, MyObject o2) {
        return o1.getStartDate().compareTo(o2.getStartDate());
    }
}
```

As you can see, the responder was able to, quite literally, fill in the gaps with the needed code for a custom comparator function (exactly what was needed to be able to compare their Objects by date) that the inquirer had mentioned wanting to try. All of this was done without wasting time doing guesswork. As a whole, the question ends up being a very useful resource as both the questions and answer work together to create an easy-to-follow guide for solving similar problems.

## In Conclusion...

Being considerate towards the people willing to help you benefits everyone in the long run. When it comes to asking smart questions, it’s especially important to take into consideration the things to avoid like providing vague descriptions or code, entitled behavior, etc. (i.e. be nice to the people trying to help you). However, it’s also noteworthy that, as I sorted through StackOverflow, a good portion of the highest ranked questions were what the authors of the smart-question-guide may consider ‘stupid’ questions. So, while it’s definitely still a good idea to do your own research and check to see if somebody else already asked/answered your question, in the words of many of many ICS professors, don’t be afraid to ask your ‘dumb’ questions, because there’s a good chance everybody else has the same question and just doesn't want to ask. (Note: this sentiment is most applicable to sites like StackOverflow that are very beginner-friendly) A simple question could still end up being really beneficial for you and many others; it might also save someone a few hours of sifting through convoluted documentation. Besides, I’ve found that a lot of people (including programmers) are more than willing to flex their knowledge and explain the simpler concepts just for the satisfaction that all the information they’ve accumulated over the years is being put to good use.

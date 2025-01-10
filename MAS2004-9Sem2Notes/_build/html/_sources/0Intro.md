# 0. Introduction

These are the official lectures notes for Semester 2 of [MAS2004 Analysis and Algebra](https://sites.google.com/sheffield.ac.uk/somasstudentintranet/programme-study-information/module-choice/somas-module-directory/somas-module-directory-202425/mas2004-analysis-and-algebra) and [MAS2009 Analysis](https://sites.google.com/sheffield.ac.uk/somasstudentintranet/programme-study-information/module-choice/somas-module-directory/somas-module-directory-202425/mas2009-analysis). 

The notes are produced with Jupyter Book, a package that uses Python and LaTeX to produce searchable maths notes that are [more accessible](https://abestshef.github.io/jupyter/Intro.html) than PDFs. 

If you have any issues using these notes, spot any errors, or would otherwise like help making best use of them, please get in touch by [emailing Rosie](mailto:r.j.shewellbrockway@sheffield.ac.uk).

## 0.1. Overview 

Analysis is a major branch of pure mathematics most concerned with the rigorous treatment of convergence and limits. In fact, you have already been doing analysis: Semester 2 of MAS107 introduced you to the analysis of real sequences. The definitions, theorems and proofs from MAS107 will be very useful in what we cover next, so make sure you have this module (or at least its notes) to hand!

This semester, the focus will be on the analysis of real functions. Specifically, the main themes will be:

- *Functional Limits.* <br> How do we definite rigorously the notion of convergence to a limit for functions? This will underpin our work on continuity and differentiability.
- *Continuity.* <br> What does it mean to say that a function is continuous? What is the "right" definition, that will give us the theorems we want and and enable us to prove them rigorously?
- *Differentiability.* <br> What is the "right" definition of differentiability, and how is it related to that of continuity? We'll prove some beautiful theorems that connect the formal definition for the derivative to geometric properties of curves. %We'll also see how differentiability can be used to approximate functions by polynomials, using Taylor's theorem.
- *Sequences and series of functions.* <br> In MAS107, you studied sequences and series of real numbers. In [Chapter 5](chap:seq&seriesoffns), we focus on sequences and series in which each term is a function, rather than a number. This allows us to rigorously define important functions such as the exponential function, in terms of a uniformly convergent power series.
- *Integration.* <br> We give a formal treatment of the Riemann integral, in terms of areas under curves. We'll prove some more famous theorems, such as the fundamental theorem of calculus, which allows us to view integration as the opposite of differentiation.

```{warning}
Just as with MAS107, we will be revisiting concepts that you have been dealing with informally for a very long time. This can make analysis deceptively difficult. For example, we know you know how to calculate $\lim_{x\rightarrow 0}\frac{1}{x+1}$ easily --- that isn't the point here. What's new and to be learnt this semester is how to prove your calculation is correct, rigorously and from first principles. 

But don't despair! Everyone finds this when they are beginning analysis training. The trick is to keep practising, get regular feedback on your work, and remember what you are doing is hard --- even if many of the concepts seem familiar to you.
```

## 0.2. Benefits of learning analysis

So why bother? There are several reasons. One is that the content of this semester covers an extremely important period of mathematical history, spanning from when Newton and Leibniz first discovered differentiation in 17th century, up to the work of Cauchy and Weierstrass in the 19th century. So you will be learning definitions and styles of proof that are completely fundamental to the way modern mathematicians work and think today.

Another reason it is important is that not all functions are "nice". The heuristic methods for finding limits and derivatives that you have met so far work very well for most functions you would care to write down. But unfortunately, these types of functions are not the ones that come up in many applications. So even if you want to study applied maths or stats in the future, you will find the methods of analysis ($\varepsilon$'s, $\delta$'s and so on) still underpin a lot of what applied mathematicians and statisticians have to care about.

A more general perk of analysis education is transferable skills --- in particular, critical thinking and problem solving. Analysis is the practice of thinking very hard and very carefully about things, and as a result, you are likely to find that other areas of maths (especially pure maths) become easier once you begin to master it. And of course, there is the obvious benefit to [employability](https://students.sheffield.ac.uk/skills/sga).


## 0.3. Recommended books

- **How to Think About Analysis, by Lara Alcock.** <br>
This is a very readable and engaging book that aims to make learning analysis accessible for students are still meeting it for the first time. Rather than giving a formal treatment of the subject matter, which these notes will do, Lara's book is intended as a companion to a module such as this one, and prioritises the development of ideas and intuition over formalism.
<br>
Links: [Library](https://find.shef.ac.uk/permalink/f/15enftp/44SFD_ALMA_DS51268789000001441); [abebooks](https://www.abebooks.co.uk/9780198723530/Think-Analysis-Alcock-Lara-0198723539/plp); [goodreads](https://www.goodreads.com/book/show/24683010-how-to-think-about-analysis).

- **Understanding Analysis, by Stephen Abbott.**<br>
This is a more traditional analysis textbook, as it is sometimes useful to see ideas presented in more than one way.
<br>
Links: [Library](https://find.shef.ac.uk/permalink/f/1lephdb/44SFD_ALMA_DS51360822510001441); [abebooks](https://www.abebooks.co.uk/9781493950263/Understanding-Analysis-Stephen-Abbott-1493950266/plp); [goodreads](https://www.goodreads.com/book/show/26457662-understanding-analysis).


## 0.4. Assessment

90\% of your grade will come from sitting an exam at the end of the module; the other 10\% will come from completing homework.

### Exam (90\%)

- MAS2009 Analysis: 1.5 hour written exam in May/June.
- MAS2004 Analysis and Algebra: 2.5 hour written exam in May/June, on both Semester 1 and Semester 2 material.

### Homework (10\%)

Each homework is "out of 1", in the sense that any reasonable attempt will receive 1 mark. So handing in a blank piece of paper might receive 0 marks, but anything that shows genuine effort will receive full credit.

More importantly than the mark, each piece of work will receive constructive feedback that you can use to improve your understanding and your written mathematics. 

**Homework release schedule for Semester 2:** <br>
| Task | Release date | Due date |
| :---: | :---: | :---: |
| Homework 1 | 11am Wednesday Week 1 | 2pm Wednesday Week 3 |
| Homework 2 | 11am Wednesday Week 3 | 2pm Wednesday Week 5 |
| Homework 3 | 11am Wednesday Week 5 | 2pm Wednesday Week 7 |
| Homework 4 (Midterm online test) | 11am Wednesday Week 6 | 2pm Wednesday Week 8 |
| Homework 5 | 11am Wednesday Week 8 | 2pm Wednesday Week 10 |

Written homework submission is via [Crowdmark](https://students.sheffield.ac.uk/digital-learning/assessments/crowdmark). A link for this will be provided with the release of each homework on Blackboard. The midterm online test is on [STACK](https://aim.shef.ac.uk/moodle/my/).

## 0.5. Where to get help

### Office hours
My office hours are 10--11am on Thursdays and Fridays in Hicks G39f. To use them, you can just show up, or [book an appointment](https://calendar.app.google/aeQArCFrWEQ92Wim9). 

Booking in advance means you will definitely be seen, and there is also the option to have the appointment online, if you would prefer that.

More generally, all staff office hours can be found in the [MaS Student Handbook](https://www.google.com/url?q=https%3A%2F%2Fsites.google.com%2Fsheffield.ac.uk%2Fsomasstudentintranet%2Four-staff%2Fstaff-office-hours&sa=D&sntz=1&usg=AOvVaw0MG5KJzsfz4xfgZcJ-B5qE).

### Blackboard discussion board
Both the MAS2004 and MAS2009 Blackboard pages have discussion boards, and these are a great place to post questions and look for answers. Of course you can email me your questions, but asking on the discussion board means that more people benefit.

### Tutorials
This module has fortnightly tutorials, starting in Week 2. Please consider asking your tutorial lead for help: a different explanation from a different person can make a big difference. And if anyone leading your tutorial gives a particularly good explanation, please let me know, so I can thank them!
# COBOL-prework1
some things to read.

One of the things perhaps you'll discover as we tread through these concepts, is how dramatic, clean and elegant
UNIX systems seem after the fact. The idea of everything is a stream of bytes, whether shell scripts, programs, executable, data files, devices, etc. and how different it is in the older ways of thinking about data, JCL and COBOL as all different kinds of computer objects.

## Articles to read before first class

Scan thru these articles before the first lecture, so we don't need to cover them.

- https://en.wikipedia.org/wiki/GnuCOBOL
- https://en.wikipedia.org/wiki/COBOL
- https://www.ibm.com/ibm/history/exhibits/mainframe/mainframe_intro.html
- https://www.ibm.com/ibm/history/exhibits/mainframe/mainframe_intro2.html
- https://www.ibm.com/ibm/history/exhibits/mainframe/mainframe_intro3.html
- https://www.ibm.com/ibm/history/exhibits/mainframe/mainframe_intro4.html
- https://en.wikipedia.org/wiki/IBM_System/360

This is meant to give you a very rough overview of the IBM ecosystem, the place where most COBOL
has been utilized. 

## White Space

One of the key things you must understand about COBOL and JCL and other languages is that they are often very
whitespace sensitive. In COBOL whitespace really matters, because of the fixed format of each and every line.
This comes from the tradition of many COBOL programs starting life as decks of computer cards.
SO, UNLIKE all the languages you've been studying recently, WHITE SPACE MATTERS in ways that seem quite fussy.
I think you'd be right in holding that opinion. Ah, C'est la vie.

## JCL - Job Control Language

One of the singular aspects of COBOL, Mainframe and IBM systems is the notion of a Job Control Language (JCL). In some very real sense, this is where the notion of Unix "shells" comes from. An interpreter that takes special commands in and around running of programs to maipulate data, programs and execution of the same. JCL is a long topic, lots of history. But even the very latest IBM operating system (z/OS) relies heavily on this JCL concept. JCL is sort of like a shell script. (sortof)

`JOBS` are the tasks you setup to run in these environments. Again, an ancient term going back into `Batch Processing` days, where computer "jobs" were run one after another in a "batch" of them.

You can take a look here. [Reusable JCL collection](https://www.ibm.com/support/knowledgecenter/zosbasics/com.ibm.zos.zjcl/toc.htm) This section of online doc takes you thru how to perform various important tasks, like say `copying a dataset to tape` :-)

``` JCL
//jobname  JOB  (start of JOB statement parameters)
//stepname EXEC PGM=IEBGENER
//SYSPRINT DD  SYSOUT=*
//SYSIN    DD  DUMMY
//SYSUT1   DD  DSN=dsname,DISP=SHR
//SYSUT2   DD  DSN=dsname,DISP=(NEW,CATLG),
//     UNIT=tapedevice,
//     VOL=SER=volser
/*
```

A weird word that you may see when researching COBOL etc, is `ABEND`

```
Definition of abend (or ABEND)
computing
: the unexpected failure of a piece of computer software
```

It can mean, not only the crash of an app, based on some error condition, but also failure due to incorrect data sets IN or OUT of a program, or a system failure, etc. It may not always been the programmer's fault or the fault in the code running the program. As in
`When the job ends, you will receive a message indicating one of three conditions: job successful, JCL error, or program abend.`

And since you know about shells on Unix-like OSs, here's a quick description of [Job Control on Unix](https://en.wikipedia.org/wiki/Job_control_(Unix)) (or in a shell), and it can help bridge the gap between what you know of shells and the weird world of JCL.

## Admiral Hopper

Finally, the original language Grace Hopper pioneered is not, in fact, COBOL. It was an earlier language
named FLOW-MATIC (https://en.wikipedia.org/wiki/FLOW-MATIC) which was the first real attempt at trying make programming
someting almost any educated person could do. It tried to leverage real english words to describe what needed to be
done to create a program. On that wikipedia page is a sample FLOW-MATIC program.

### and that's enough history for now.
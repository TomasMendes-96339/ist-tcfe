# Circuit Theory and Electronics Fundamentals (CTEF): Laboratory Classes

Here you can find instructions for the CTEF laboratoty classes.

## Prerequisites

### Operating System

These classes use a recent version of the Ubuntu operating system: 18.4 or 20.4 versions.

### Required software

Git. If not pre-installed do:

``sudo apt install git``

Latex full installation:

``sudo apt install texlive-full``

LibreOffice (open-source alternative to Microsoft Office used only for
drawings):

``sudo apt install libreoffice``

If needed install more LibreOffice packages as required.

Octave (open-source alternative to Matlab):

```
sudo apt install octave
sudo apt install octave-signal
sudo apt install octave-control
```

Ngspice (open-source Spice circuit simulation tool):

```
sudo apt install ngspice
sudo apt install ngspice-doc
```


## Git Setup


Login or create a Github account if you do not own one.

Go to https://github.com/jjts/ist-tcfe.git using a browser.

Click the "Fork" button on the upper-right corner. 

You now have a copy of the example repository at
https://github.com/your_github_user/ist-tcfe.git, which is where you will place
all your work for the whole semester.


Now you need download a local copy (*clone*) of your repository:

``git clone https://github.com/your_github_user/ist-tcfe.git``

Note that you should clone your fork and not the original example repository,
because you cannot write to it. Now *cd* into the example T0 lab assignment:

``cd ist-tcfe/t0``

To run the T0 lab assignment do 
`` make`` 

This action will generate all drawings, Octave and Ngspice
files needed to produce the final report (*report.pdf*).

To start working on the T1 lab assignment, type

``cd .. && cp t0 t1 && cd t1``

To check the status of your repository clone, do

``git status`` 

It will say all directories and files including and below directory *t1* are *Untracked* by
git. This is fine so far.

Do your work modifying *t1*'s contents. 


After you are done, anybody will be able to reproduce your work
by running your top *Makefile*:

``make``

To delete every file that is generated by software, except the final *report.pdf* file, type

``make clean``

Only original source files and *report.pdf* should be kept after this
action. This guarantees that the project can be evaluated and other developers
can continue it.

Some basic notions about *bash*, the Linux terminal command interpreter, *git*
and *make* will be given in the theory classes. Apart from that, the Internet is
full of information about these popular tools, at just a Google search away.

At this point, you are ready to *commit* and *push* your work to your Github
repository, so the instructor can review and evaluate it. To commit your work in
your local clone you need to *stage* your changes first:

``cd .. && git add .``

The ``cd ..`` command will move you to the root of your repository and the ``git
add .`` command will stage all new and modified files below it. Now do

``git status``

This action gives you a last chance to review what will be committed. You can
un-stage any undesired *file* with the command

``git reset file``

Once you are happy with your staged files do the following:

``git commit -m"my fabulous commit message"``

where *my fabulous commit message* should concisely and precisely specify the
contents of the commit. To see the history of commits type

``git log``

This command is invaluable for future references and debug actions, so make sure
your commit messages are clear enough. If you now do 

``git status``

the tool will report that your local clone is ahead of the *remote* or
*upstream* repository by one commit. To send your changes to your Github
repository do

``git push``

This action will sync your clone with your remote. Your group colleagues can get
your changes in their local clones by typing

``git pull``

This will merge your changes in their clones. However, if one of them has
modified the same lines of the same file, she will get a *merge conflict* after
the pull request. Merge conflicts can be solved by the following steps
  * edit the conflict files and find the conflicting parts that are identified
    by easy to spot markers
  * correct the conflicting parts and delete the conflict markers
  * save the file
  * fix all conflicting files using the above steps
  * commit and push you changes

## How to do the lab assignment

All assignments consist of a circuit to be analysed theoretically and by simulation. The report has four parts:
* Introduction 
* Theoretical analysis
* Simulation analysis
* Conclusion

### Introduction

This section should state the learning objective of the work, describe the
circuit to be analysed referring to a figure, and summarise the theoretical and
simulation procedures in the following sections. Two to three paragraphs should
suffice with a maximum of 250 words.

Drawings *must* be done using LibreOffice Draw. Like in a real organisation, to
promote collaboration and peer review, everybody must use the same tools, no
matter if they are not the best ones. The drawings are edited with the Graphical
User Interface (GUI) and saved in the OpenDocument format (*.odg*). Only the
source *.odg* files should be committed and your Makefile *must* have a target
to automatically convert all *.odg* files into pdf files to be included in the
Latex documents. The Makefile in the example T0 assignment illustated this
process.

For the same reason, the text *must* be written in Latex, which happens to be
the best tool out there for technical writing. Read the example report and
figure out how it is setup to be partially generated automatically from data
produced by other programs such as Octave and Ngspice.

### Theoretical

Theoretical analysis *must* be supported by the Octave maths tool. All data
plots or data tables *must* be generated by an Octave script, which should also
produce the body of the respective Latex tables *automatically*. This is also
illustrated in lab assignment T0. This procedure ensures that the Octave code
and the text are always in sync.

*No formulae* should be derived in this section. The laboratory classes should
use formulae, not derive them. Mathmatical derivation is a subject for the
theory classes *only*.


### Simulation

Simulation analysis *must* be supported by the Ngspice simulation tool. All data
plots or data tables *must* be generated by an Ngspice script, which should also
produce the body of the respective Latex tables *automatically*. This is also
illustrated in lab assignment T0, using the Makefile and bash commands to
help. This procedure ensures that the Ngspice code and the text are always in
sync.




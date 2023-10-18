# Python Authoring Environments & Object Oriented Workflows

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>This tutorial was written by Katherine Walden and is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

## Lab Goals & Objectives

This lab provides an introduction the additional funtionality of console-based Python IDEs (Spyder) and notebook-based IDEs (Jupyter Lab). It also introduces students to aspects of how Python functions as an object-oriented language, specifically classes, objects and inheritance.

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
<td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?pid=c9223a74-1b88-4f51-bea7-af34014538b0">Lecture/live coding playlist</a></td>
  </tr>
  </table>

## Acknowledgements

The documentation for Google Colab was developed by Spring 2021 graduate teaching assistant [Subhadyuti Sahoo](https://github.com/SDSAHOO703).

Peer review and editing was provided by Spring 2021 graduate teaching assistants [Subhadyuti Sahoo](https://github.com/SDSAHOO703) and [Aidan Draper](https://github.com/adraper2).

The author consulted the following resources when writing the "Python authoring environments" sections:
- Al Sweigart's [*Automate the Boring Stuff With Python*](https://nostarch.com/automatestuff2) (No Starch Press, 2020).
  * Chapter 11, "Debugging" (249-266)
- Allen Downey, [*Think Python: How to Think Like a Computer Scientist*](https://www.oreilly.com/library/view/think-python-2nd/9781491939406/) (O'Reilly, 2015).
  * Chapter 2 "Variables, Expressions and Statements" (11-20)
- Quinn Dombrowski, Tassie Gniady, and David Kloster, "Introduction to Jupyter Notebooks," *The Programming Historian* 8 (2019), https://doi.org/10.46430/phen0087

The author consulted the following the following resources when writing the object-oriented workflows sections:
- Dave Braunschweig, "[Objects and Classes](https://press.rebus.community/programmingfundamentals/chapter/objects-and-classes/)" in *Programming Fundamentals* (Rebus Press, 2018).
- Dave Braunschweig, "[Encapsulation](https://press.rebus.community/programmingfundamentals/chapter/encapsulation/)" in *Programming Fundamentals* (Rebus Press, 2018).
- Dave Braunschweig, "[Inheritance](https://press.rebus.community/programmingfundamentals/chapter/inheritance_and_polymorphism/)" in *Programming Fundamentals* (Rebus Press, 2018).
- Eric Matthes, "Chapter 9: Classes" in *Python Crash Course, 3rd edition* (No Starch Press; 2023). [Link to online access through Hesburgh Libraries](https://onesearch.library.nd.edu/permalink/f/1phik6l/ndu_aleph006326301).
- Allen B. Downey, "Chapter 15: Classes and Objects" in *Think Python: How to Think Like A Computer Scientist, 2nd edition* (O'Reilly: 2016). [Link to access through Hesburgh Libraries](https://onesearch.library.nd.edu/permalink/f/1phik6l/ndu_aleph005139341).

# Table of Contents

- [Lecture & Live Coding](#lecture--live-coding)
- [Setup & Environment](#setup--environment)
- [Lab Notebook Template](#lab-notebook-template)
- [Authoring Enviornments](#authoring-environments)
  * [Python in Spyder](#python-in-spyder)
  * [Python & Jupyter Notebooks](#python--jupyter-notebooks) 
- [Object-Oriented Workflows](#object-oriented-workflows)
  * [Code Reuse & Modularity (aka a quick detour into modules, packages, and libraries)](#code-reuse--modularity-aka-a-quick-detour-into-modules-packages-and-libraries)
- [How to Submit This Lab (and Show Your Work)](#how-to-submit-this-lab-and-show-your-work)
- [Lab Notebook Questions](#lab-notebook-questions)

[Click here](https://colab.research.google.com/drive/1dxyRiPaa0IWDfvDXrf_xYcMJsAKSaixx?usp=sharing) to access the lab procedure as a Jupyter Notebook (Google Colab, ND Users).

# Lecture & Live Coding

Throughout this lab, you will see a Panopto icon at the start of select sections. This icon indicates there is lecture/live coding asynchronous content that accompanies this section of the lab. You can click the link in the figure caption to access these materials (ND users only).

Example:

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
<td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?pid=c9223a74-1b88-4f51-bea7-af34014538b0">Lecture/live coding playlist</a></td>
  </tr>
  </table>

# Setup & Environment

<p align="center"><a href="https://github.com/kwaldenphd/python-jupyter-notebooks/blob/main/images/Figure_1.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/python-jupyter-notebooks/blob/main/images/Figure_1.png?raw=true" /></a></p>

Windows/PC instructions:
- Anaconda Documentation, ["Installing on Windows"](https://docs.anaconda.com/anaconda/install/windows/) *Anaconda* (2020).
- ProgrammingKnowledge, ["Install Anaconda Python, Jupyter Notebook and Spyder on Windows 10"](https://youtu.be/5mDYijMfSzs) *YouTube video* (4 September 2018).

Mac OS instructions:
- Anaconda Documentation, ["Installing on macOS"](https://docs.anaconda.com/anaconda/install/mac-os/) *Anaconda* (2020).
- Understanding Data, ["Easily Install Anaconda Python Distribution On Mac OS X"](https://youtu.be/V6ZAv7hBH6Y) *YouTube video* (16 October 2019).

Chromebook instructions:
- Alex P. Miller, ["Data Science on a Chromebook: How to run Jupyter, Python, and R locally in ChromeOS"](https://alex.miller.im/posts/data-science-chromebook-pixelbook-jupyter-python-r/) *personal blog* (6 March 2019).
- Noebrian, ["Installing Anaconda on a Chromebook"](https://chromebook.home.blog/2019/01/20/installing-anaconda-on-a-chromebook-no-dev-beta-or-crouton-needed/) *ChromeBooks* (20 January 2019).

<p align="center"><img src="https://github.com/kwaldenphd/python-authoring-environments/blob/main/images/Anaconda_Navigator.png?raw=true" width="1000"></p>

Once you are able to launch the Anaconda Navigator, click on the icons for the following two programs to install them:
- Spyder
- JupyterLab

# Lab Notebook Template

[Click here](https://colab.research.google.com/drive/1e5SDiIxZVpMU_t_uQqv3MeTC0hYBwEYE?usp=sharing) to access the lab notebook template as a Jupyter Notebook (Google CoLab, ND Users).

To download the notebok from Google Colaboratory (as a `.ipynb` file): 
- `File` (top-left corner) -> `Download` -> `Download as .ipynb`
- Once you have downloaded the file on your local computer, you can move it into a designated folder for this lab/class.

What folks will submit for this lab will include a Jupyter Notebook (`.ipynb`) file with responses to the lab questions. Upload the file to the Canvas assignment.
- If working in Google Colab, a shared link submission is fine.

# How to Submit This Lab (and show your work)

Moving forward, we're going to be submitting lab notebooks using the provide Jupyter Notebook template ([link for this lab's template](https://colab.research.google.com/drive/1e5SDiIxZVpMU_t_uQqv3MeTC0hYBwEYE?usp=sharing)).
- If working in JupyterLab (or another desktop IDE), download the `.ipynb` file to your local computer
  * `File` - `Download` - `Download as .ipynb`
- If working in Google Colaboratory, MAKE SURE you save a copy to your local drive. Otherwise your changes will not be saved.
  * `File` - `Save a copy in Drive`

The lab notebook template includes all of the questions as well as pre-created markdown cells for narrative text answers and pre-created code cells for any programs you may need to create. 
- Double click on these cells to edit and add your own content
- If questions do not require a code component, you can ignore those cells
- If questions to not require a narrative component, you can ignore those cells

If working in JupyterLab or another desktop IDE, upload the lab notebook template `.ipynb` file to Canvas as your lab submission.

If working in Google Colaboratory, submit the link to your notebook (checking sharing permissions, similar with Google Docs).

# Authoring Environments 

Up to this point, we have used the browser-based IDE [Replit](https://repl.it/).

What is an IDE? "An integrated development environment (IDE) is a software application that provides comprehensive facilities to computer programmers for software development. An IDE normally consists of at least a source code editor, build automation tools and a debugger" ([Wikipedia](https://en.wikipedia.org/wiki/Integrated_development_environment)).

An IDE can include features like syntax highlighting, code completion, version control, and debugging. There are a WIDE range of IDEs that are proprietary or open-source, tailored to a specific language or able to work across languages.

Some common IDEs include Eclipse, Geany, Brackets, Atom, PyCharm, Spyder, RStudio, etc. For more in IDEs, visit Wikipedia's ["Comparison of integrated development environments"](https://en.wikipedia.org/wiki/Comparison_of_integrated_development_environments) page.

Replit (generally) worked for (most of) our needs. But it ran into problems with more complex programs or programs involving external files/datasets/etc. Now, we're going to install Python on your local computer, using a distribution called Anaconda.

<blockquote>"Anaconda is a open-source distribution of the Python and R programming languages for scientific computing (data science, machine learning applications, large-scale data processing, predictive analytics, etc.), that aims to simplify package management and deployment. The distribution includes data-science packages suitable for Windows, Linux, and macOS. It is developed and maintained by Anaconda, Inc., which was founded by Peter Wang and Travis Oliphant in 2012." (<a href="https://en.wikipedia.org/wiki/Anaconda_(Python_distribution)">Wikipedia</a>)</blockquote>

The Anaconda environment includes a number of specific tools and programs, including:
- JupyterLab
- Jupyter Notebook
- Qt Console
- Spyder
- Glue
- Orange
- RStudio
- Visual Code Studio

To install Anaconda on your own computer:

Windows/PC instructions:
- Anaconda Documentation, ["Installing on Windows"](https://docs.anaconda.com/anaconda/install/windows/) *Anaconda* (2020).
- ProgrammingKnowledge, ["Install Anaconda Python, Jupyter Notebook and Spyder on Windows 10"](https://youtu.be/5mDYijMfSzs) *YouTube video* (4 September 2018).

Mac OS instructions:
- Anaconda Documentation, ["Installing on macOS"](https://docs.anaconda.com/anaconda/install/mac-os/) *Anaconda* (2020).
- Understanding Data, ["Easily Install Anaconda Python Distribution On Mac OS X"](https://youtu.be/V6ZAv7hBH6Y) *YouTube video* (16 October 2019).

Chromebook instructions:
- Alex P. Miller, ["Data Science on a Chromebook: How to run Jupyter, Python, and R locally in ChromeOS"](https://alex.miller.im/posts/data-science-chromebook-pixelbook-jupyter-python-r/) *personal blog* (6 March 2019).
- Noebrian, ["Installing Anaconda on a Chromebook"](https://chromebook.home.blog/2019/01/20/installing-anaconda-on-a-chromebook-no-dev-beta-or-crouton-needed/) *ChromeBooks* (20 January 2019).

<p align="center"><img src="https://github.com/kwaldenphd/python-authoring-environments/blob/main/images/Anaconda_Navigator.png?raw=true" width="1000"></p>

Once you are able to launch the Anaconda Navigator, click on the icons for the following two programs to install them:
- Spyder
- JupyterLab

The rest of this lab will introduce us to `Spyder`, a Python IDE with some similarities to Replit, and `JupyterLab,` a Python notebook authoring IDE. Not sure what notebooks are? Stay tuned!

## Python in Spyder

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
<td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=ba8b6fcf-2ae6-4e7d-9a2d-af3401369491">Python in Spyder</a></td>
  </tr>
  </table>

To install Spyder as a stand-alone program: [spyder-ide.org](https://www.spyder-ide.org)

"Spyder is a free and open source scientific environment written in Python, for Python, and designed by and for scientists, engineers and data analysts. It features a unique combination of the advanced editing, analysis, debugging, and profiling functionality of a comprehensive development tool with the data exploration, interactive execution, deep inspection, and beautiful visualization capabilities of a scientific package" ([Spyder documentation](https://www.spyder-ide.org/)).

Spyder's core components include:
- Editor
- IPython console
- Variable explorer
- Plots
- Debugger
- Help

These robust Python features in Spyder will be incredibly useful as we start to do more work with datasets, visualizations (plots), and debugging in more complex programming environments.

<p align="center"><img src="https://github.com/kwaldenphd/python-authoring-environments/blob/main/images/Anaconda_Navigator.png?raw=true" width="1000"></p>

Open the Anaconda navigator and select the option to launch Spyder.

<p align="center"><img src="https://github.com/kwaldenphd/python-authoring-environments/blob/main/images/Spyder_Navigation.png?raw=true" width="1000"></p>

Spyder has three default panes that show up when you launch the program. Your `.py` file shows up on the left-hand side of the program window. This is where you will write Python code. You can have multiple `.py` files open in Spyder and navigate between the tabs. 

The top-right pane has four default options:
- Variable explorer, which lets you see named variables in your program
- Help, which provides additional documentation, information, or resources
- Plots, which will show visualizations generated by your program
- Files, which will show all files currently open or active in your Spyder workspace

The bottom-right pane is the Console, which lets you execute and test Python commands. You can have multiple consoles open simultaneously. So how is the Console different from your `.py` file?

In the `.py` file you are writing a Python program that will run or execute when the file is called. You can make updates to that file, save changes, etc. The Console lets you execute Python commands but is not saving those commands as part of a `.py` file. Great for testing. Less great for building out complex programs.

When we were working in Replit, all files that were part of our Python project were in the same virtual workspace. That's not going to be the case when working in a desktop IDE like Spyder. Think of this as the difference between working with files in Google Drive versus on your local computer. 

You can set a working directory, which is where Spyder will look for external files you are wanting to access from within a Python program. The working directory is also where Python will save `.py` files you build.

<p align="center"><img src="https://github.com/kwaldenphd/python-authoring-environments/blob/main/images/Spyder_Directory.png?raw=true" width="250"></p>

Click on the folder icon in the top-right hand corner of Spyder (next to the arrow icon) to set a working directory. It doe--where you save `.py` files and other files (think data files) you might be wanting to access as part of a Python program. 

Now, files don't have to be in your current working directory for you to access them in Python. But you'll need to provide the full file path (i.e. location information or directory information for where that file is located on your computer).

Go ahead and create an `EoC` folder and set that folder as your working directory in Spyder. It might also be a good idea to start creating lab-specific sub-folders within your `EoC` parent folder. This will help with organization as we move through labs and work with a variety of sample files and datasets.

<blockquote>Q1: Work through the <a href="https://docs.spyder-ide.org/current/videos/first-steps-with-spyder.html">"First Steps with Spyder"</a>resources provided in the Spyder documentation. That includes two 3.5 minute videos that introduce you to the basics of the Spyder IDE and how to get started with Python in Spyder. Describe your experience getting  started with Spyder using  these materials/resources.</blockquote>

<blockquote>Q2: Take a program (<code>.py</code> file) from a previous lab or collaborative problem solving session and load it into Spyder. Explore how the program runs in a different IDE. In particular, explore Spyder's options to run portions or a selection of the larger program. How does this change the way you interact with the program?</blockquote>

### Debugging

To paraphrase an old programming joke, writing code is 90% of the work of programming. Debugging is the other 90%. You've been working on a program for hours, your head hurts, and something still isn't working. We all know a version of that feeling.

There's no easy solution that will prevent all problems (or "bugs") in your code. But having strategies for testing your code, recognizing and making sense of error messages, and methodically debugging your code can help immensely.

Python errors will usually fall into three types: syntax, runtime, and semantic.

- Syntax refers to the structure of a program and rules about that structure. ***Syntax errors*** involve things like indentation, parenthesis, etc. The Python interpreter expects the language to be structured a specific way, and throws a syntax error when it's not.

- ***Runtime errors***, or ***exceptions***: appears after a program has started running. These errors indicate something unexpected has happened that interrupts or stops the program execution. 
  * Things that can cause a runtime error include:
    * Misspelled or incorrectly capitalized variables or function names
    * Dividing by zero
    * Mismatched data types (i.e. attempting to perform operations on data of the wrong type)
    * Attempting to use a type conversion function on a value that can't be converted

- Semantic: relates to meaning. ***Semantic errors*** have to do with the meaning (or purpose/intent) of your code. Semantic errors don't show up as error messages-but the program will not do what you expect it to do. 

The debugging strategies discussed here will focus on semantic errors but are useful for all types of errors.

#### Stepwise Debugging in Spyder

Spyder will catch many syntax and runtime errors. Hover over a red `X` by any of your lines of code to see more information about a possible error.

Spyder integrates the enhanced `ipdb` debugger, which gives you robust options for troubleshooting or debugging your code. Specifically, the debugger will let you run a program line by line, running a single line of code and waiting for you to tell it to continue.

Running your program through this kind of debugging is immensely valuable for tracking down bugs or catching complex issues in a program. This mode of debugging includes the following possible steps or "moves":
- Continue (run the program until the next breakpoint)
- Step in (executes the next line of code; if the next line of code is a function, the debugger will 'step into' the first line of that function)
- Step over (executes the next line of code, but will not go line-by-line through the function; the debugger 'steps over' the function code and waits for the function call to return)
- Step out (lets you step out of a function if you used step in and want to 'step out' of the function)
- Stop (stops debugging and terminates the program)

<p align="center"><img src="https://github.com/kwaldenphd/python-authoring-environments/blob/main/images/Spyder_Debugging_Menu.png?raw=true" width="250"></p>

<p align="center"><img src="https://github.com/kwaldenphd/python-authoring-environments/blob/main/images/Spyder_Debugging.png?raw=true" width="500"></p>

Let's use this approach and Spyder functionality to debug a function program we wrote for a previous lab.

```Python
# function definition
def printNTimes(message, x):
 for x in range(x):
  return message

# get inputs
phrase = input("Enter your message here: ") # input statement for string
times = int(input("How many times do you want this statement to print? Enter a number value.")) # input statement for number of times

# function call
print(printNTimes(message, x))
```

First run the program without the debugger enabled. What happens? Debug the file going line-by-line. Remember to use `Step Over` to execute functions without going into each line of the function code.
- Functions in this sample program include `print()` and `input()`
- You can always `Step Out` if you accidently step into a function

<blockquote>Q3: What type of error does this program return (syntax, runtime, semantic) and why? How would we go about modifying the program to address this error?</blockquote>

<blockquote>Q4: How is Spyder different than previous IDEs? What do you see as strengths/advantages? What do you see as possible challenges?</blockquote>

#### Other Debugging Approaches

If you're interested in exploring other Python debugging workflows, specifically using `log`, Prof. Walden has prepared [an introductory guide](https://github.com/kwaldenphd/python-workflows/blob/main/logging.md).

## Python & Jupyter Notebooks

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
<td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=4b9db2a4-f8b7-4cac-ac23-af340138ffb5">Python & Jupyter Notebooks</a></td>
  </tr>
  </table>

"The Jupyter Notebook is a web-based interactive computing platform that allows users to author data- and code-driven narratives that combine live code, equations, narrative text, visualizations, interactive dashboards and other media." (Project Jupyter, [Jupyter Notebook](http://cameronoelsen.github.io/jupytersite/))

<p align="center"><img src="https://github.com/kwaldenphd/python-authoring-environments/blob/main/images/Google_Colab.png?raw=true" width="1000"></p>

Navigate to [the following link](https://colab.research.google.com/drive/1vyAHwOf76_byT1CY8ofFwBg67h3Sljuh?usp=sharing#scrollTo=Thlyy-KwFmdR) in a web browser. You're looking at a Jupyter Notebook in the Google Colaboratory cloud-based IDE. And the content in this notebook may be familiar- it's the instructional materials from one of our previous labs.

<p align="center"><img src="https://github.com/kwaldenphd/python-authoring-environments/blob/main/images/Colab_ToC.png?raw=true" width="500"></p>

Scroll through the notebook, making use of the table of contents. Run some of the code cells and see what happens. 

As the definition provided above highlights, Jupyter Notebooks are an authoring environment that lets you bring together narrative text, code, and output, all in a single document. 

There's a lot to love about notebooks as an authoring environment, and the notebook format (Jupyter Notebooks for Python, RMarkdown files for R/RStudio, etc) are increasingly becoming the norm in coding classes and data science workflows.

A few challenges or drawbacks:
- Version control especially in collaborative environments is virtually impossible
- Notebooks often lack the debugging tools and autocompletion features of other IDEs
- Testing and debugging code is virtually impossible
- Installing third-party packages or modules can be tricky 
- The notebook non-linear workflow for program development/documentation limits transparent reproducible code
- In some cases, notebooks don't play well with external big data applications (spark/dask/distributed)

<blockquote>Citation: Alexander Mueller, <a href= "https://towardsdatascience.com/5-reasons-why-jupyter-notebooks-suck-4dc201e27086">"5 reasons why jupyter notebooks suck"</a>, <i>Towards Data Science</i> (24 March 2018)</blockquote>

So when could you use Jupyter notebooks? Jupyter notebooks are fantastic tools for exploration. They also work well for documenting process, or in situations when you might need to alternate between code and other kinds of text (like say in a lab notebook).

### What is Jupyter?

"Project Jupyter is a non-profit, open-source project, born out of the IPython Project in 2014 as it evolved to support interactive data science and scientific computing across all programming languages. Jupyter will always be 100% open-source software, free for all to use and released under the liberal terms of the modified BSD license" (["About Us"](https://jupyter.org/about), *Jupyter.org*)

Project Jupyter receives funding from a range of non-profit foundations and corporate partners that include:
- Alfred P. Sloan Foundation
- Gordon and Betty Moore Foundation
- Google
- Microsoft

Institutional partners for Project Jupyter include:
- Apple
- Bloomberg
- Netflix
- Cal Poly
- Berkeley
- Amazon Web Services (AWS)

The name Jupyter is a reference to the three core languages supported by the project: **Ju**lia, **Py**thon, and **R**. And what is a Jupyter notebook? According to "[The Jupyter Notebook](https://jupyter-notebook.readthedocs.io/en/stable/notebook.html)" documentation:

<blockquote>The notebook extends the console-based approach to interactive computing in a qualitatively new direction, providing a web-based application suitable for capturing the whole computation process: developing, documenting, and executing code, as well as communicating the results. The Jupyter notebook combines two components:
 <ul>
  <li>A web application: a browser-based tool for interactive authoring of documents which combine explanatory text, mathematics, computations and their rich media output.</li>
  <li>Notebook documents: a representation of all content visible in the web application, including inputs and outputs of the computations, explanatory text, mathematics, images, and rich media representations of objects</li>
 </ul>
 </blockquote>
 
### Launching & Navigating JupyterLab

<p align="center"><img src="https://github.com/kwaldenphd/python-authoring-environments/blob/main/images/Anaconda_Navigator.png?raw=true" width="1000"></p>

A Jupyter notebook is a file (the notebook document) that displays or renders in a web browser. We'll be launching Jupyter Notebooks through Anaconda. The web application component of the notebook will be hosted on your local computer and the notebook document will save to a file directory on your local computer.

<p align="center"><img src="https://github.com/kwaldenphd/python-authoring-environments/blob/main/images/JupyterLab_Navigation.png?raw=true" width="1000"></p>

It may take some time for the notebook to open in a browser window. The notebook name is what the `.ipynb` file created via the Jupyter notebook will be saved as. Click on the default notebook name (usually `Untitled`) to rename the notebook.

<p align="center"><img src="https://github.com/kwaldenphd/python-authoring-environments/blob/main/images/JupyterLab_Menu_Icons.png?raw=true" width="500"></p>

The menu bar includes drop-down options used to manipulate the notebook functionality. The toolbar icons give you quick access to the most commonly-used features of the notebook environment.

### Authoring in Jupyter Notebooks

Once you've created a new Jupyter Notebook, we can start adding cells. What's this about cells? Have we entered an alternate College of Science universe? Code cells are the default type of cell. But why are there cells? Jupyter notebooks consist of a sequence of cells.

A **cell** is a multiline text input field. You can execute the contents of a cell by using `Shift-Enter`, clicking the `Play` button in the toolbar, or the `Cell` and `Run` icons in the menu bar. How a cell executes is determined by its type.

There are three types of Jupyter notebook cells.
- ***Code cells*** allow you to edit and write code with full syntax highlighting and tab completion.
- ***Markdown cells*** allow you to document the computational process using descriptive text formatted using the markdown language.
- ***Raw cells*** allow you to write output directly. These cells are not evaluated by the notebook and render unmodified. NOTE- not all notebook authoring environments support raw cells

You can edit or work within a code cell until you get the desired output, then move on to a new cell. You can use markdown cells along the way to document your process using narrative text (alongside or in addition to code comments used in code cells).

To learn more about formatting text in markdown, visit Adam Pritchard's ["Markdown Cheatsheet"](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) resource page.

<p align="center"><img src="https://github.com/kwaldenphd/python-authoring-environments/blob/main/images/JupyterLab_Menu_Icons.png?raw=true" width="500"></p>

There are a few ways you can change a cell's type. One option is to select the cell type from the drop-down options. Another option is to select `Cell Type` from the `Cell` menu tab. 

<blockquote>Q5: In a markdown cell, add text that includes the following style or formatting components:
 <ul>
  <li>Heading (h1, h2, h3, etc)</li>
  <li>Italics or bold text formatting</li>
  <li>Unordered (or bulleted point) list</li>
  <li>Link</li>
 </ul>
 NOTE: You will want to reference Adam Pritchard's <a href="https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet">Markdown Cheatsheet</a> resource when working on this question.
 </blockquote>

<blockquote>Q6: In a code cell, write a simple Python program (or programs) that includes the following functions:
 <ul>
  <li><code>input()</code></li>
  <li><code>print()</code></li>
 </ul>
 You are welcome to use a program (or programs) you've written for previous labs- original code is not required for this question. The main point for this question is to see how a Jupyter Notebook code cell executes a program.</blockquote>

### Google CoLab: A Web-Based Alternative

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
  <td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=baea6963-c832-4d27-a1cf-add90131468f">Google CoLab</a></td>
  </tr>
  </table>

Anaconda is a hefty software program that may not run (or run well) on your personal computer. If Jupyter Notebooks through Anaconda is not a good fit, Google CoLab is a robust alternative.

<blockquote>"'Colaboratory,' or 'CoLab' for short, is a product from Google Research. Colab allows anybody to write and execute arbitrary python code through the browser, and is especially well suited to machine learning, data analysis and education. More technically, Colab is a hosted Jupyter notebook service that requires no setup to use, while providing free access to computing resources including GPUs." (<a href="https://research.google.com/colaboratory/faq.html">Google Colaboratory, "Frequently Asked Questions"</a>)</blockquote>

Google CoLab is a web-based notebook authoring environment that supports some level of collaboration and sharing, similar to other aspects of the Google Drive infrastructure.
- ["Google CoLab Instructions"](https://github.com/kwaldenphd/python-authoring-environments/blob/main/google-colab-instructions.md), developed by Spring and Fall 2021 graduate teaching assistant [Subhadyuti Sahoo](https://github.com/SDSAHOO703).
- See also: ["Welcome to Colaboratory"](https://colab.research.google.com/notebooks/intro.ipynb) notebook from Google CoLab

# Object-Oriented Workflows

So far, our work in Python has focused on **procedural programming**, which Busbee and Braunschweig describe as...
- "A series of computational steps to be carried out...The focus of procedural programming is to break down a programming task into a collection of variables, data structures, and subroutines" (CITATION: https://press.rebus.community/programmingfundamentals/chapter/objects-and-classes/)

Object-oriented paradigms treat data types as an abstraction, **objects**. This lets us move beyond a particular programming language's built-in data types and data structures to have programming structures, **classes**, that are suited for particular data types and workflows. 

## Classes

Our work with functions is one step in the direction of object-oriented workflows. Let's walk through an example from Busbee & Braunschweig's *Programming Fundamentals* that illustrates the move from procedural to object-oriented programming workflows.
- Citation: Dave Braunschweig, "[Objects and Classes](https://press.rebus.community/programmingfundamentals/chapter/objects-and-classes/)" in *Programming Fundamentals* (Rebus Press, 2018).

<blockquote>"Objects and classes are often designed to represent real-world objects. Consider a door as an example of a real-world object. Most doors have limited functionality. They may be opened and closed, and locked and unlocked. In procedural programming, we might design functions to open, close, lock, and unlock a door, such as:</blockquote>

```
# procedural programming with functions
OpenDoor(door)
CloseDoor(door)
LockDoor(door)
UnlockDoor(door)
```

*Prof. Walden's note: In this example, door is still an object, but the functions that reference the object aren't connected or associated with it.*

<blockquote>"Object-oriented programming combines code and data, so that, rather than having separate functions act on doors, we design doors that have methods that can act on themselves. Methods represent something the object can do, and are typically defined using verbs. Object-oriented door pseudocode might look like:</blockquote>

```
# object-oriented programming with methods
door.Open()
door.Close()
door.Lock()
door.Unlock()
```

*Prof. Walden's note: In this example, the door is an object that exists in the program via a class, and the actions are arguments that act on the object.*

<blockquote>"Objects may also have attributes, something the object is or has, and are typically defined using nouns or adjectives. Door attributes might include:</blockquote>

```
# attributes that could be part of the class
door.Height
door.Width
door.Color
door.Closed
door.Locked
```

<blockquote>"When we write code to define a generic door, we would create a door class. The door class would contain all of the methods a door can perform and all of the attributes a door might have. We would then create instances of the class (objects) to represent specific doors, such as a front door, back door, or room door on a house, or a left door and right door on a car."</blockquote>

So let's move this into Python, creating a `dog` class that incocporates a few key attributes and actions (i.e. `methods`). Some core components of our class...
- Creating the `dog` object
- Assigning attributes, specifically `name` and `age`
- Determining actions, specifically `sit` and `roll over`

```Python
# this example is adapted from Chapter 9, pp 158, in Eric Matthes' _Python Crash Course_ book

class Dog: # initiate the class
 """A simple attempt to model a dog"""

  def __init__(self, name, age): # initial function to create the object and assign some attributes
   """Initialize name and age attributes"""
   self.name = name
   self.age = age

  def sit(self): # function to assign sit method
   """Simulate a dog sitting in response to a command"""
   print(f"{self.name} is now sitting.")

 def roll_over(self): # function to assign roll_over method
   """Simulate rolling over in response to a command"""
   print(f"{self.name} is rolled over!")
```

As with other function definitions, this program doesn't return any output. Let's walk through this example:
- `class` initiates the class
- `__init__` is the initial function
- The `self` parameter (you could call this anything, but this exapmle uses `self`) references the current instance of the class
- Subsequent named functions (using the `def` keyword) assign additional atrributes or actions

The `Dog` class could refer to any `dog` abstraction- let's create an **instance** of the class, specific for the Walden family dog, Sandy Koufax.

SANDY PICTURE

```Python
myDog = Dog('Sandy', '9') # create an instance of the class
print(f"My dog's name is {myDog.name}.") # output instance attribute
print(f"My dog is {myDog.age} years old.") # output instance attribute
```

We can use the `dot notation (.)` to access attributes or call methods from the class.

```Python
myDog.sit() # sit method
myDog.roll_over() # roll over method
```

A quick recap:
- An `object` is a programming abstraction that brings together data and procedures. Object-oriented programming workflows are an alterative to strictly procedural workflows.
- A `class` is Python's mechanism for creating an object. Classes can include `methods` and `attributes`.
- An `instance` is a particular instance of a `class`.

## Inheritance

Let's imagine a scenario in which you need to create classes for members of the Notre Dame community. You might need specific classes for `undergraduate students`, `graduate students`, `faculty`, `staff`, `alumni`, `family members`, etc. While the classes would be different, they would all likely share some common elements.

Rather than repeat all of those common elements, we could use **inheritance** to create a hierarchy of classes. We could start with a parent `person` class that lays out the common elements, and then create sub-classes that would have distinct properties but also **inherit** properties from the parent class. 

To put that another way:

<blockquote>"Inheritance is a way of arranging objects in a hierarchy from the most general to the most specific. An object which inherits from another object is considered to be a subtype of that object. An example might include Instructor and Student, each of which inherit from Person. When we can describe the relationship between two objects using the phrase is-a, that relationship is inheritance." (Dave Braunschweig, "<a href="https://press.rebus.community/programmingfundamentals/chapter/inheritance_and_polymorphism/">Inheritance and Polymorphism</a>" in <em>Programming Fundamentals</em></blockquote>

Let's create our parent (or `base`) class, `Person`.

```Python
class Person: # assign class
  def __init__(self, fname, lname): # initial function
    self.firstname = fname # first name
    self.lastname = lname # last name

  def printname(self): # printname function
    print(self.firstname, self.lastname)
```

To create an instance of the parent class:

```Python
x = Person("Knute", "Rockne") # create instance
x.printname() # use printname method
```

Now let's create a `Student` subclass.

```Python
class Student(Person): # assign subclass
 def __init__(self, fname, lname): # initial function
  super().__init__(fname, lname) # super function to inherit parent properties
  self.graduationYear = year # new properties for the subclass
  self.classYear = classYear
  self.major = major
  self.hall = hall

def intro(self): # new method for the subclass
  print(f"{self.firstname} {self.lastname} is a {self.classYear} majoring in {self.major}, and lives in {self.hall}. They will graduate in Spring {self.graduationYear}.")
```

Then, we can create an instance of the `Student` subclass.

```Python
y = Student("Knute", "Rockne") # create instance

Student.graduationYear = '1914' # assign values to attributes
Student.major = 'Chemistry & Pharmacology'
Student.hall = 'Sorin Hall'

Student.intro() # access subclass method
```

### Additional Resources

We're just scratching the surface for object-oriented programming workflows (in general and in Python).

For more conceptual background:
- Dave Braunschweig, "[Objects and Classes](https://press.rebus.community/programmingfundamentals/chapter/objects-and-classes/)" in *Programming Fundamentals* (Rebus Press, 2018).
- Dave Braunschweig, "[Encapsulation](https://press.rebus.community/programmingfundamentals/chapter/encapsulation/)" in *Programming Fundamentals* (Rebus Press, 2018).
- Dave Braunschweig, "[Inheritance](https://press.rebus.community/programmingfundamentals/chapter/inheritance_and_polymorphism/)" in *Programming Fundamentals* (Rebus Press, 2018).

For more on objects & classes (and related concepts) in Python:
- Eric Matthes, "Chapter 9: Classes" in *Python Crash Course, 3rd edition* (No Starch Press; 2023). [Link to online access through Hesburgh Libraries](https://onesearch.library.nd.edu/permalink/f/1phik6l/ndu_aleph006326301).
- Allen B. Downey, "Chapter 15: Classes and Objects" in *Think Python: How to Think Like A Computer Scientist, 2nd edition* (O'Reilly: 2016). [Link to access through Hesburgh Libraries](https://onesearch.library.nd.edu/permalink/f/1phik6l/ndu_aleph005139341).

If you're on the hunt for decent online Python resources, a couple not terrible starting points...
- [Geeks for Geeks, "Python Classes and Objects"](https://www.geeksforgeeks.org/python-classes-and-objects/)
- [W3Schools, "Python Classes and Objects"](https://www.w3schools.com/python/python_classes.asp)
- [W3Schools, "Python Inheritance"](https://www.w3schools.com/python/python_inheritance.asp)

If you really want to get into the Python weeds...
- [Python documentation on classes](https://docs.python.org/3/tutorial/classes.html)

### Comprehension Check

<table>
 <tr><td>
<img src="https://github.com/kwaldenphd/internet/blob/main/images/clipboard.png?raw=true" alt="Clipboard icon" width="50"/></td>
  <td><a href="https://docs.google.com/forms/d/e/1FAIpQLSegWqG-EsbjRi1zgWHKZ8TEJpAvskGuvO2V9QkbniQelA4ZnA/viewform?usp=sf_link">Object-Oriented Workflows Comprehension Check</a></td>
  </tr>
  </table>

## Code Reuse & Modularity (aka a quick detour into modules, packages, and libraries)

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
<td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=e652072c-176a-4490-b7b3-af360164bf8a">Modules, Packages & Libraries</a></td>
  </tr>
  </table>

As we move forward in Python, we're going to be encountering the terms `package`, `module`, and `library.` All of these terms refer to external Python programs that we can use in our program without having to recreate the entire original code. We can think of these resources as "expansion packs" for Python that expand or extend the programming language's built-in functionality.

A few preliminary definitions...
- A ***module*** is a Python file that typically includes specialized functions and variables. Modules typically have `.py` file extensions.
- A single or simple directory of modules is called a ***package***. Packages are typically a simple directory with multiple modules.
- A ***library*** includes blocks of code that can be reused within a program. Libraries are a collection of modules that have a much more complex directory/sub-directory/etc structure than packages

Some modules, packages, and libraries are built-in to Python and require no additional installation. Others have to be installed (typically at the command line, or in the terminal) before you can import and use them in a program.

Built-in functions don't require any extra steps to be able to access them in the programming environment. For example, you can see the source code for the `print()` function, contained in Python's [bltinmodule.c](https://github.com/python/cpython/blob/main/Python/bltinmodule.c#L1972) file in the [source code](https://github.com/python/cpython/blob/). But all we have to do is use the function name in our program.

<p align="center"><img src="https://github.com/kwaldenphd/python-functions/blob/main/images/python_package.png?raw=true" width="500"></p>

In this example, we have a `game` package that includes `sound`, `image`, and `level` sub-packages. Each of those sub-packages includes specific modules. For example, the `sound` sub-package includes the `load.py`, `play.py`, and `pause.py` modules.

We can bring these modules into our program using an `import` statement.

For example, let's say we wanted to bring the `start.py` module from the `level` sub-package into our program.

We could do this using the following `import` statement at the start of our program.

```Python
from game.level import start
```

Now, we would be able to access any of the functions (or other code) contained in the `start.py` module, because we have **imported** them into our program.

For more on modules, packages, and libraries in Python:
- Programmiz, "[Python Package](https://www.programiz.com/python-programming/package)
- GeeksForGeeks, "[What is the difference between Python's Module, Package and Library?](https://www.geeksforgeeks.org/what-is-the-difference-between-pythons-module-package-and-library/)" (30 September 2022)
- John Sturtz, "[Python Modules and Packages - An Introduction](https://realpython.com/python-modules-packages/)" *Real Python*

### Comprehension Check

<table>
 <tr><td>
<img src="https://github.com/kwaldenphd/internet/blob/main/images/clipboard.png?raw=true" alt="Clipboard icon" width="50"/></td>
  <td><a href="https://docs.google.com/forms/d/e/1FAIpQLSctIknF2mA209zKSFH7lAA_6dBg9HoAmYDBg58QqNk37YgBVA/viewform?usp=sf_link">Code Reuse & Modularity in Python Comprehension Check</a></td>
  </tr>
  </table>

# How to Submit This Lab (and show your work)

Moving forward, we're going to be submitting lab notebooks using the provide Jupyter Notebook template ([link for this lab's template](https://colab.research.google.com/drive/1e5SDiIxZVpMU_t_uQqv3MeTC0hYBwEYE?usp=sharing)).
- If working in JupyterLab (or another desktop IDE), download the `.ipynb` file to your local computer
  * `File` - `Download` - `Download as .ipynb`
- If working in Google Colaboratory, MAKE SURE you save a copy to your local drive. Otherwise your changes will not be saved.
  * `File` - `Save a copy in Drive`

The lab notebook template includes all of the questions as well as pre-created markdown cells for narrative text answers and pre-created code cells for any programs you may need to create. 
- Double click on these cells to edit and add your own content
- If questions do not require a code component, you can ignore those cells
- If questions to not require a narrative component, you can ignore those cells

If working in JupyterLab or another desktop IDE, upload the lab notebook template `.ipynb` file to Canvas as your lab submission.

If working in Google Colaboratory, submit the link to your notebook (checking sharing permissions, similar with Google Docs).

# Lab Notebook Questions

[Click here](https://colab.research.google.com/drive/1e5SDiIxZVpMU_t_uQqv3MeTC0hYBwEYE?usp=sharing) to access the lab notebook template as a Jupyter Notebook (Google CoLab, ND Users).

To download the notebok from Google Colaboratory (as a `.ipynb` file): `File` (top-left corner) -> `Download` -> `Download as .ipynb`. Once you have downloaded the file on your local computer, you can move it into a designated folder for this lab/class.

Q1: Work through the <a href="https://docs.spyder-ide.org/current/videos/first-steps-with-spyder.html">"First Steps with Spyder"</a>resources provided in the Spyder documentation. That includes two 3.5 minute videos that introduce you to the basics of the Spyder IDE and how to get started with Python in Spyder. Describe your experience getting  started with Spyder using  these materials/resources.

Q2: What type of error does this program return (syntax, runtime, semantic) and why? How would we go about modifying the program to address this error?

```Python
# function definition
def printNTimes(message, x):
 for x in range(x):
  print(message)

# get inputs
phrase = input("Enter your message here: ") # input statement for string
times = int(input("How many times do you want this statement to print? Enter a number value.")) # input statement for number of times

# function call
printNTimes(message, x)
```

Q3: Take a `.py` file from a previous lab and load it into Spyder. Explore how the program runs in a different IDE. In particular, explore Spyder's options to run portions or a selection of the larger program. How does this change the way you interact with the program?

Q4: How is Spyder different than previous IDEs? What do you see as strengths/advantages? What do you see as possible challenges?

Q5: In a markdown cell, add text that includes the following style or formatting components:
- Heading (h1, h2, h3, etc)
- Italics or bold text formatting
- Unordered (or bulleted point) list
- Link

NOTE: You will want to reference Adam Pritchard's <a href="https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet">Markdown Cheatsheet</a> resource when working on this question.

Q6: In a code cell, write a simple Python program (or programs) that includes the following functions:
- `input()`
- `print()`

You are welcome to use a program (or programs) you've written for previous labs- original code is not required for this question. The main point for this question is to see how a Jupyter Notebook code cell executes a program.

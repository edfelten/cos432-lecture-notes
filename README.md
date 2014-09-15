COS 432 - Lecture Notes
=======================

Student-created lectures notes for COS 432: Information Security
at Princeton University. To access the notes, you should install
[git](http://git-scm.com/book/en/Getting-Started-Installing-Git) and 
[LaTeX](https://en.wikibooks.org/wiki/LaTeX/Installation). If you are new to
LaTeX, see the additional [installation instructions](#latexinstruct) below.
If you wish to contribute to the notes, you will need to configure git to
[authenticate with Github](https://help.github.com/articles/set-up-git#next-steps-authenticating-to-github-from-git)
and follow the steps below.

Access
------

To pull the notes to your local computer you must first `clone` the repository.
In the terminal, navigate to the root directory where you'd like the notes to
be located and enter:

    git clone https://github.com/ewfelten/cos432-lecture-notes.git
    cd cos432-lecture-notes

You will see a series of `.tex` files in this folder, which are the latex
source files broken down by lecture. To read the files as a pdf, you must
compile them with the following command:

    pdflatex InfoSec

Once compiled, you should see `InfoSec.pdf` which contains notes from all
lectures.

If your classmates update the notes, you can pull down the newest changes by
executing the following command in the notes directory:

    git pull origin master

Remember to run `pdflatex InfoSec` after the pull to build the new version of
the pdf.

Contribute
----------

If you'd like to make changes to the notes, you will have to do so in your own
repository and create a [pull request](https://help.github.com/articles/using-pull-requests). 
First, you need to `fork` the repository on Github. 

- Navigate to the [repository page](https://github.com/ewfelten/cos432-lecture-notes)
- Click the fork button and follow the instructions ![fork
    button](https://github-images.s3.amazonaws.com/help/repository/fork_button.jpg)
- In the terminal, navigate to the root directory where you wish to store the
    notes
- Clone the forked repo locally

        git clone https://github.com/YOUR_USERNAME/cos432-lecture-notes.git cos432-lecture-notes-fork
        cd cos432-lecture-notes-fork
        git remote add upstream https://github.com/ewfelten/cos432-lecture-notes.git

- Make changes to relevant `.tex` files
- Build your changes using `pdflatex InfoSec` and make sure they look correct
- Commit your local changes
        
        git add -A .
        git commit -a -m "A SUMMARY OF YOUR CHANGES"

- Sync your repo with upstream changes (you may need to
    [fix conflicts](https://stackoverflow.com/questions/161813/fix-merge-conflicts-in-git))
        
        git fetch upstream
        git checkout master
        git merge upstream/master

- Once merges are done, push your changes to your remote fork on Github
        
        git push origin master

- On the Github page for your forked repository, you can then create a pull
    request. If you are unsure how to do so, we recommend following the [Github
    tutorial](https://help.github.com/articles/using-pull-requests#before-you-begin).

<a name="latexinstruct"></a>LaTeX Instructions
----------------------------------------------

Latex `.tex` files can be edited with any standard text editor, but there are
many [editors](https://en.wikibooks.org/wiki/LaTeX/Installation#Editors) which
provide highlighting and live previews of edits in pdf form.

Your default latex install may not include all the required packages. You
should install the following packages to ensure you have the proper
dependencies:

### Debian-based Linux

    sudo apt-get install texlive-base texlive-latex3 texlive-math-extra texlive-latex-extra texlive-pstricks

### MacOSX

Help your classmates by submitting a pull request with this info

### Windows

- If your LaTeX environment is a recent version of
    [MiKTeX](http://miktex.org/), you can install the necessary
    dependencies using the MiKTeX Package Manager. Note, if this is your
    first install, we recommend restarting your computer before continuing.
- Run the MiKTeX Package Manager with administrator privileges either
    via the start menu or by finding the executable in the folder you 
    installed MiKTeX in, under `miktex\bin\mpm_mfc_admin.exe`. 
- After opening, first synchronize your packages with the remote repository 
    by going to the "Repository" menu and selecting "Synchronize".
- Then find and install the following packages by right clicking on their 
    names and selecting "Install":
        - `amsmath`
        - `amscls`
        - `mathtools`
        - `fancybox`
        - `pgf`
        - `xcolor`
        - `rotating`
        - `url`
        - `fancyhdr`
        - `mptopdf`

        > Note that this may not be an exhaustive list of all
        dependencies required. If the build finds other missing
        dependencies, try using the Install button on the MiKTeX popup
        window. Alternatively, try searching for the names of the 
        missing packages (denoted by files ending in .sty) using the 
        "Keywords" box in the Package Manager. If any packages are found 
        for the search, try installing those as well. 
- The next time you execute `pdflatex InfoSec`, the packages should be configured 
    and the course notes should be build properly.

Contributors and License
------------------------

These notes were initially created by Brenda Hiller '13, with
help from Anna Kornfeld Simpson '14 and Connie Wan '13, for
the Fall 2012 offering of COS 432.  Further contributors are
reflected in the Github revision history.

This work is copyrighted by its authors.
For information on licensing of this work, see the file LICENSE.

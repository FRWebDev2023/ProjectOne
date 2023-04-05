In this problem set, you'll practice creating a basic web page using HTML and CSS. You will also practice using Jest to run unit tests, as well as using `git` and GitHub to manage, submit, and publish assignments for this course.

This problem set will thus be structured a little bit differently than future problem sets, requiring you do more command line and `git` work.

Step 1. Getting Setup
---------------------

To complete this problem set, follow these steps. If you get stuck (particularly with installation issues), ask Ms. Hughes for help!

Download and install [**Node.js**](https://nodejs.org/en)



You will also need to install the [**Jest**](https://facebook.github.io/jest/) test runner in order to test that your code meets specifications. You should install this program _globally_, since you will use it on multiple problem sets:

    npm install -g jest

You can confirm that Jest has correctly been installed with

    jest --version

You should see `v24.9.0` or higher (if it is a lower version, use `npm update -g jest` to update).

Note: you should be running these commands in your terminal

### Cloning and Branching the Repo


Each of your in-class assignments in this course will be completed on a branch of the project repo. 


After finding the project 1 repo, `clone` the repo to your local machine so you can edit the files.

After navigating to your repo locally, run the command to create your own branch:

    git checkout -b first-last

### Install Dependencies

In order to run the included unit tests for this problem set, you will need to install a number of dependencies listed in the included `package.json` file:

From the _root directory_ of the repo (outside of the `problem-a` folder), quickly install the dependencies using `npm install`. This will install the required files in the `node_modules` directory of this particular project. It may take a minute. Note that you may see some _Warnings_ about peer dependencies; you can ignore those. But if you see any _Errors_, check in with us about how to fix them!


Step 2. Running the Tests
-------------------------

The problem sets in this class will support a [Test-Driven Development](https://en.wikipedia.org/wiki/Test-driven_development) approach: you will be provided with a program that automatically _tests_ your code for correctness, with your task being to fill in the code that makes the tests pass.

*   Tests for each problem are defined in the `problem.spec.js` file found in each problem folder. These tests are written in JavaScript using the Jest framework, which we will discuss later in the course. But you should be able to sort of make sense of the code if you look at it.

**BEFORE YOU DO ANY CODING**, first run the included tests using the Jest test runner via the `jest`, specifying as an argument that you want to run the tests for `problem-a`:

    jest problem-a

Because you haven't written any code yet, the tests should (almost) all fail! That's okay—it just means you have a list of things to do.

![Example of failing tests](https://canvas.uw.edu/courses/1223074/files/50628565/preview)

If you don't get a failure message that looks similar to the one above, check that you've installed the software and are running the tests correctly. Tests can fail either because the code is incorrect or because the test environment is not set up correctly!

**To pass the first test** and demonstrate that you've gotten your tests running, _copy and paste_ the complete output of this initial test run (everything from after you typed `jest problem-a` to the next command prompt) and save it in a new file called **`pretest.txt`** (**inside the `problem-a` directory**). If you run the tests again, you should now see the first one pass!

To practice with git, be sure and `add` and `commit` this file to your repo (`"Add pretest results"` is a good commit message).

Note that you can have Jest _automatically_ re-run tests whenever you change a file by using

    jest problem-a --watch

It's normal to have the Jest be running in one terminal, the _live-server_ running in a second, and a third in which you are entering commands e.g., for `git`

Step 3. Making the Web Page
---------------------------

The next step is to complete the problem (in the `problem-a` folder). Create the web page so that the tests pass! Your task is to create a simple web page that describes _a fictional character that you admire_. This can be any character from a movie, television series, book, comic, song, or story. The page will include the character's name, a short description of the character, a picture, some reasons you admire that character, and a link to another web page that provides more information about the character or the story. Choose your character and then continue with the rest of the steps.

As you work on this, remember to save and commit your work regularly. For example, you might commit your changes once you finish each step or two.

You'll need to find an picture of your character on the Internet and download that image to the problem directory (so inside the `problem-a` folder). Save it in a new folder called **`img/`** (you can create this folder from the command line using the `mkdir` command!).

Long file names and spaces in file names are generally a bad idea when building web sites, as they make resources harder to refer to. If the file you just downloaded contains spaces in the file name, you should replace those spaces with hyphens (**`-`**) or just remove them. You should also make the file name all lower-case letters to reduce chances for errors, and shorten the name if it is excessively long. Lastly, pay attention to the file extension as well as the file name (e.g., `.jpg` or `.png`). When referring to image files in your web pages, you must specify the **entire** file name, including its extension.

If the picture file is really big (larger than a megabyte), you might want to use a graphics tool to reduce it in size. If you are on a Mac, you can use the [built-in Preview application](http://www.wikihow.com/Resize-Pictures-(for-Macs)) to do that. On Windows, you can use the [built-in Photo Gallery application](https://www.digitalunite.com/guides/digital-photography/how-resize-photos). Your target height is 400 pixels, so there's no need for the image to be any larger than that.

### The HTML

We have provided you the `index.html` file for you to use, but you will need to fill in its contents using VS Code (or your preferred text editor). You can start with the [web page template](https://info340.github.io/html-fundamentals.html#web-page-template), but be sure to include the following elements:

1.  A [title](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title) for the page that is the name of your character—the browser will show this title in the browser tab, and search engine indexers will treat this as the title of the page.
    
2.  Metadata that gives _your_ name as its [author](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta).
    
3.  A [top-level heading](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) with the character's name.
    
4.  An [image](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) of the character, specifically the one you downloaded to the `img` subdirectory. Note that the `src` attribute will need to use the **relative path** to the file... and it's inside the `img` folder!
    
    *   _Do not_ include a width or height attribute—use CSS to specify the image's appearance size instead.
        
    *   _Do_ include a description of the image in the `alt` attribute. This will be used by assistive technologies such as screen readers for the blind, as well as search indexers.
        
5.  A [paragraph](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) with a short description of the character. This only needs to be a couple sentences.
    
    *   Within that description, include the name of what movie/series/book/comic/song/story the character is from, and make that name be a [hyperlink](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) to another existing web page that tells me more about the work (a Wikipedia or IMDB page is fine). Bonus: also use the [proper element for the title of a work](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/cite).
6.  A [list](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) of at least **3** reasons you admire this character. Your reasons can be as detailed and as serious or silly as you like. Your list can either be _ordered_ or _unordered_ (you could theoretically use a [descriptive list](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl), but it isn't supported by the tester).
    

### The CSS

You should also add some CSS to make the page look a little nicer. We have provided a `css/style.css` file for you to use, but you will need to fill in the rules.

1.  You will need to [link](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) the CSS file into the HTML. Be sure to use a relative path for the file!
    
2.  The content of the page's `body` should have a [font size](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) of `16px` (making that a "default" for the page).
    
3.  Similarly, the page's `body` should have a [font](http://www.w3schools.com/cssref/pr_font_font-family.asp) of `'Helvetica Neue'`, followed by `Helvetica`, `Arial`, and finally `sans-serif` if the others aren't available.
    
4.  Paragraphs should have a [line height](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height) of 1.5x the normal line height. _Check the documentation carefully for how to format this value._
    
5.  [Constrain the height](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height) of the page images to be no more than `400` pixels. If your image is already smaller than that, you won't notice any difference in appearance, but this will ensure that the image is no more than 400 pixels tall, regardless of the actual size of the image file.
    
6.  _One_ item in your list (your choice) should be given a [color](https://developer.mozilla.org/en-US/docs/Web/CSS/color) other than the default black to highlight it as _important_. Use a **class selector** to apply this rule; this means you will need to modify the HTML to give one list element a `class` attribute. Be sure to use a semantic name for your class!
    

Check your web page BOTH by opening the `.html` file in a web browser and looking at it, _and_ by running the included tests using Jest. You will only get credit for problem sets if any included tests pass!

You need to check both the functionality and the tests for problems—you cannot just rely on one or the other! I recommend developing the functionality, then checking tests at the end (or end of each step).

When you have finished the web page and are satisfied with your work, be sure to `add` and `commit` your work. `"Add completed character page"` is a good commit message.

Step 6. Submit Your Solution
----------------------------

In order to submit assignments in this class, you will need to:

1.  `push` your completed work to your GitHub repository.
    
3.  Submit both (1) a link to your branch **_and_** (2) a screenshot of the tests passing in your terminal
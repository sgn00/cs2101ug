---
layout: page
title: User Guide
---

SWEe! is a  **desktop app for CS2103T students to manage their learning progress mainly through flashcards**. It is optimized for CLI users so that frequent tasks can be done faster by typing in commands. If you can type fast, SWEe! can create your CS2103T flashcards faster than traditional GUI apps.


* Table of Contents
    - [Introduction](#introduction)
    - [Quick start](#quick-start)
    - [Application layout](#application-layout)
    - [Notes about the command format](#notes-about-the-command-format)
    - [Common Input Fields](#common-input-fields)
    - [Features](#features)
        - [Add a flashcard](#add-a-flashcard--add): `add`
        - [Clear all flashcards](#clear-all-flashcards--clear): `clear`
        - [Delete a flashcard](#delete-a-flashcard---delete): `delete`
        - [Edit a flashcard](#edit-a-flashcard---edit): `edit`
        - [Filter for flashcards](#filter-for-flashcards---filter): `filter`
        - [Favourite a flashcard](#favourite-a-flashcard---fav) : `fav`
        - [Unfavourite a flashcard](#unfavourite-a-flashcard---unfav): `unfav`
        - [Find flashcards](#find-flashcards--find): `find`
        - [View help](#view-help--help): `help`
        - [List all flashcards](#list-all-flashcards--list): `list`
        - [Review flashcards](#review-flashcards-review) : `review`
        - [Quiz flashcards](#quiz-flashcards-quiz): `quiz`
        - [Sort all flashcards](#sort-all-flashcards--sort): `sort`
        - [View a flashcard](#view-a-flashcard---view): `view`
        - [View the statistics of a flashcard](#view-the-statistics-of-flashcard--stats): `stats`
        - [Exit the program](#exit-the-program--exit): `exit`
        - [Saving the data](#saving-the-data)
    - [FAQ](#faq)
    - [Command summary](#command-summary)
        

--------------------------------------------------------------------------------------------------------------------
## Introduction

![filedirectory](images/ug/logo_image.jpg)

#### Welcome to SWEe! (Software Engineering Everyday)! 😊

Thank you for downloading our application. We look forward to your continuous support and appreciate your feedback to help us improve our application. 

#### What is SWEe!?

SWEe! is a desktop application with a command line interface (CLI) for CS2103T students to manage their learning progress through flashcards. With a CLI, you will be able to perform tasks and navigate to different functionalities of the application more quickly,  allowing you to save precious time for other tasks

#### SWEe! is perfect for:

* Organising key learning points from the textbook in 2103T website  in a single platform
* Testing your knowledge of the content taught with the help of SWEe’s quiz mode
* Tracking your progress and monitor which topics you are weak using SWEe’s statistics functionality

#### So, is SWEe! for you?

* Are you a busy CS2103T student who needs more time to focus on other modules such as CS2100 or CS2101?
* Do you get frustrated navigating the CS2103T website?
* Do you want to score well in your examinations?

I’m sure you want to score in your examination 😊 so please proceed on to this user guide to discover the formula for scoring well in your exam. 
<div style="page-break-after: always;"></div>

## Quick start

1. Grab your CS2103 notes before we get started.

1. Ensure you have Java `11` or above installed in your Computer. But how? Well, follow the steps below to check your Java version. 
   
   Step 1: Open your terminal. Type in `java --version` and press *Enter*.

   Step 2: You will now be able to check the Java version installed in your Computer!

   ![Java Version](images/quick-start/javaVersion.png)


1. Download the latest `swee.jar` from [here](https://github.com/AY2021S1-CS2103T-T17-2/tp/releases).<br>

    ![Download Swee Jar](images/quick-start/downloadSweeJar.png)

1. Copy the file to the folder you want to use as the _home folder_ for SWEe!.

1. Double-click the file to start the app. The GUI similar to the image below should appear in a few seconds. Note how the app contains some sample data. <br>

    ![Quick Start UI](images/QuickStartUi.png)
    <div style="page-break-after: always;"></div>
<br>
1. At the top of the screen, type the command in the command box and press Enter on your keyboard to execute it. E.g. typing help and pressing Enter will open the help window.

1. Refer to the [Features](#features) below for details of each command.

<div style="page-break-after: always;"></div>

## Application layout

The figures below show the annotated version of the graphic user interface. This will help you better identify the various sections and elements in the application, as well as understand the technical terms stated in this documentation.

![filedirectory](images/ug/label1.png)

![filedirectory](images/ug/label2.png)

<div style="page-break-after: always;"></div>

## Notes about the command format
Feeling a little overwhelmed by the command format we use throughout the user guide? Fear not, as this section will guide you along the various command formats and notations we use throughout the user guide!


Format/Notation | Meaning
-----------|-----------------------
`QUESTION` | Words in uppercase are parameters that you should supply. <br> E.g. in `add q/QUESTION`, `QUESTION` is a parameter which can be used as `add q/What is my name?`
`q/QUESTION` | The letter and slash before the parameter is the prefix. You should use this to separate the current parameter from other parameters.
`success` | Words in lowercase are to be specified exactly, meaning word for word. 
`<success|reviewed>` | Items in angle brackets are either/or options. Each option is delineated by a `|`. <br> E.g. `<success|reviewed>` can be used as success or reviewed but not both
`[c/CATEGORY]` | Items in square brackets are optional. You can choose whether you want to specify them. <br> E.g. `q/QUESTION [c/CATEGORY]` can be used as `q/What is my name? c/Name` or `q/What is my name?`
`[t/TAG]...` | Items with ellipsis after them can be used either multiple or zero times <br> E.g. `t/TAG` can be used 0 times or as `t/friend`, `t/friend t/family`, etc

<div markdown="span" class="alert alert-primary">

:bulb: **Tip:** Parameters can be specified in any order. If the command specifies `q/QUESTION a/ANSWER`, you can specify it as `a/ANSWER q/QUESTION` as well 
</div> 

<div style="page-break-after: always;"></div>

## Common Input Fields

Many of our commands use the same input fields. This section will teach you what each of them mean and how to specify them.
If you are reading this guide for the first time, you can skip to [Features](#features) first. You can refer back to this table at any time!

<br>

Input Field | What is it & How to specify
-----------|-----------------------
`q/QUESTION`    | Question on the flashcard.<br>`QUESTION` has no character restrictions so you can input anything you like.
`a/ANSWER`      | Answer on the flashcard.<br>`ANSWER` has no character restrictions so you can input anything you like.
`c/CATEGORY`    | Category of the flashcard.<br>`CATEGORY` must be alphanumeric and can be multiple words.
`r/RATING`      | Star rating of the flashcard.<br>`RATING` must be a number between 1 and 5 inclusive.
`d/DIAGRAM`     | Diagram (image) of the flashcard.<br>`DIAGRAM` must be a valid path to a file. <br>eg. It can be a full file path such as C:/users/tom/Desktop/image/diagram.png<br> eg. It can be a relative file path (relative to swee.jar) such as images/image.jpg<br>Only supports the following image file types: jpg, png, jpeg, bmp
`n/NOTE`        | Note on the flashcard.<br>`NOTE` has no character limit or restrictions so you can input anything you like.
`t/TAG`         | These are tags of the flashcard. A flashcard can have more than one tag.<br>`TAG` must be alphanumeric and must be a single word.
`INDEX`         | `INDEX` refers to the index number shown in the displayed flashcard list.<br>Every visible flashcard on the display list has an `INDEX`.<br>`INDEX` is always a positive integer greater than 0. eg. 1, 2, 3, …
`KEYWORD`       | `KEYWORD` can be alphanumeric or punctuations. `KEYWORD` should not contain spaces.

<div style="page-break-after: always;"></div>

## Features

### Add a flashcard : `add`

Adds a flashcard.

Format: `add q/QUESTION a/ANSWER [c/CATEGORY] [r/RATING] [n/NOTE] [d/DIAGRAM] [t/TAG]...`

* Refer to [common input fields](#common-input-fields) on what the different fields are and how to specify them.
* After a new flashcard is added, all flashcards will be listed. 

<div markdown="span" class="alert alert-primary">

:bulb: **Tip:** If the category is not specified, the flashcard will have the <b>General</b> category.

</div>

Examples:
* `add q/What does OOP stand for? a/Object Oriented Programming`
* `add q/What does OOP stand for? a/Object Oriented Programming r/3 t/cool`
* `add q/What does OOP stand for? a/Object Oriented Programming c/Super Important n/Important question!`
* `add q/What does OOP stand for? a/Object Oriented Programming d/images/diagram.png`
* `add q/What does OOP stand for? a/Object Oriented Programming c/UML n/Important question! d/images/diagram.png`

<div style="page-break-after: always;"></div>

**Steps for adding a flashcard with diagram**:

**Step 1**: Locate the relative file path of the image file. In this example, our file path is `images/classDiagramExample1.png` 

Root folder containing the jar file        |  Image directory
:-------------------------:|:-------------------------:
![filedirectory](images/ug/ug_add_step1.png) |  ![filedirectory](images/ug/ug_add_step1.1.PNG)

<div style="page-break-after: always;"></div>

**Step 2**: Type the command `add q/This is an example of a class diagram a/True d/image/classDiagramExample1.png` and press Enter. Remember to include the file extension in `DIAGRAM`

![filedirectory](images/ug/ug_add_step2.png)

<div style="page-break-after: always;"></div>

**Step 3**: The flashcard is added to the list.

![filedirectory](images/ug/ug_add_step3.png)

<div style="page-break-after: always;"></div>

### Clear all flashcards : `clear` 

Clears all flashcard data from the program.

Format: `clear`


### Delete a flashcard  : `delete`

Realised that a flashcard is now useless or irrelevant? You can simply remove it from your list using our delete command!

Format: `delete INDEX`

* Deletes the flashcard at the specified `INDEX`. The `INDEX` refers to the index number shown in the displayed flashcard list.
* `INDEX` must be a positive integer eg. 1, 2, 3, …

Example: `delete 3` deletes the 3rd flashcard in the flashcard list.

**Steps for deleting a flashcard**:

**Step 1**: Locate the flashcard you want to delete. In this example, we want to delete the 3rd flashcard from the list. Type `delete 3` into the command box and press Enter 

![filedirectory](images/ug/ug_delete_step1.png)

**Step 2**: The result display will display a message telling you that the flashcard has been deleted 

**Step 3**: The list view will show the updated flashcard list, with the specified flashcard removed

![filedirectory](images/ug/ug_delete_step2.png)

<div style="page-break-after: always;"></div>


### Edit a flashcard  : `edit`

Yes, we all make mistakes (and typos). Realised that you have a typo in your flashcard? Fret not, you can edit your flashcard details in SWEe! by specifying the fields you want to edit!

Format: `edit INDEX [q/QUESTION] [a/ANSWER] [c/CATEGORY] [n/NOTE] [r/RATING] [d/DIAGRAM] [t/TAG]...`

* Edits the flashcard at the specified `INDEX`. The `INDEX` refers to the index number shown in the displayed flashcard list.
* A minimum of one field has to be given.
* Specifying empty values to `NOTE`, `RATING`, `TAG` or `DIAGRAM` eg. `r/` will remove the corresponding field in the flashcard.

Examples:

* `edit 3 q/What does OOP stand for? c/Acronyms` edits the 1st flashcard’s question and category to be What does OOP stand for? and Acronyms respectively.
* `edit 3 a/Object Oriented Programming t/` edits the 3rd flashcard’s answer and clears all existing tags
* `edit 3 n/Important question! r/` edits the 3rd flashcard’s note and clears rating

<div style="page-break-after: always;"></div>

**Steps for editing a flashcard**:

**Step 1**: Locate the flashcard you wish to edit. In this example, we want to edit the first flashcard's question and category to What does OOP stand for? and Acronyms respectively. Type `edit 1 q/What does OOP stand for? c/Acronyms` into the command box and press Enter

![filedirectory](images/ug/ug_edit_step1.PNG)
<div style="page-break-after: always;"></div>

**Step 2**: The result display will show a message that the flashcard has been edited successfully

**Step 3**: The list view will show the updated details of the flashcard after the edit

![filedirectory](images/ug/ug_edit_step2.PNG)

<div style="page-break-after: always;"></div>

### Filter for flashcards  : `filter`

Filters for specific flashcard(s) based on the field input(s) by the user. 
This will return all the flashcards whose fields match all the fields specified by the user.

Format: `filter [c/CATEGORY] [r/RATING] [f/<yes|no>] [t/TAG]...`

* Filters the specified flashcard based on category, rating, favourite status or tags.
* Refer to [common input fields](#common-input-fields) on what the different fields are and how to specify them.
* Specifying `f/yes` filters for favourited flashcards while `f/no` filters for unfavourited flashcards.
* Supports filtering of one or more different fields. For example:
    - `filter c/SDLC r/5` will filter out flashcards belonging to the SDLC category with a rating of 5.
* Although all fields are optional, a minimum of one field has to be given.
<div markdown="span" class="alert alert-primary">:memo: Note:
<code>filter r/</code> will filter for all unrated flashcards.</div>

<div markdown="span" class="alert alert-primary">

:bulb: **Tip:** Want to list all your flashcards after using `filter`? Use the [list](#list-all-flashcards--list) command.

</div> 

Examples:
*  `filter c/SDLC` filters and lists all flashcards belonging to the SDLC category.
*  `filter t/examinable t/study` filters and lists all flashcards that have both an “examinable” tag and a “study” tag.
*  `filter r/3 f/yes` filters and lists all favourited flashcards that have a rating of 3.
*  `filter f/no f/yes c/General` filters and lists all favourited flashcards that belong to the General category.
    (only last instance of f/ is read)

<div style="page-break-after: always;"></div>
**Steps for filtering for a flashcard based on category and tag**:

**Step 1**: We want to filter for a flashcard which has a Trivial category and contains the preloaded tag. Type the command `filter c/Trivial t/preloaded` and press Enter.

![filedirectory](images/ug/ug_filter_step1.PNG)

**Step 2**: The flashcard with the category Trivial and tag field preloaded is shown.

![filedirectory](images/ug/ug_filter_step2.PNG)

<div style="page-break-after: always;"></div>

### Favourite a flashcard  : `fav`

Favourites the specified flashcard.

Format: `fav INDEX`

* Favourites the flashcard at the specified `INDEX`. The `INDEX` refers to the index number shown in the displayed flashcard list.
* `INDEX` must be a positive integer **greater than 0**. eg. 1, 2, 3, …

Examples: 
* `list` followed by `fav 2` favourites the 2nd flashcard in the displayed flashcard list.

### Unfavourite a flashcard  : `unfav`

Unfavourites the specified flashcard.

Format: `unfav INDEX`

* Unfavourites the flashcard at the specified `INDEX`. The `INDEX` refers to the index number shown in the displayed flashcard list.
* `INDEX` must be a positive integer **greater than 0**. eg. 1, 2, 3, …

Examples: 
* `list` followed by `unfav 2` unfavourites the 2nd flashcard in the displayed flashcard list.

<div style="page-break-after: always;"></div>

### Find flashcards : `find`

Want to find a particular flashcard but too lazy to check through all the flashcards individually to find it? We understand your pain and fear not, let SWEe! take away your pain by doing the finding for you! Keep your flashcards coming as we will provide an quick and easy way for you to search for anything and everything no matter how many flashcards you have.

Format: `find KEYWORD [KEYWORD]...`

* Refer to [common input fields](#common-input-fields) on how to specify the different fields.
* The keywords are **case insensitive**.

<div markdown="span" class="alert alert-primary">

:memo: Note: If you search for multiple keywords, flashcards containing either of the keywords will be returned. For example, "General OOP" will return flashcards containing either General and/or OOP. 

</div>

<div markdown="span" class="alert alert-primary">

:bulb: **Tip:** Want to list all your flashcards after using `find`? Use the [list](#list-all-flashcards--list) command.

</div> 

Examples: 
* `find general` displays all flashcards containing the word general.
* `find general important` displays all flashcards containing either the word general and/or important.
* `find -` displays all flashcards containing "-".

<div style="page-break-after: always;"></div>

**Steps for finding flashcards**:

**Step 1**: To find flashcards containing the keyword "SDLC", type `find SDLC` in the *Command Box* and press *Enter*.

![Find Step 1](images/ug/ug_find_step1.png)

<div style="page-break-after: always;"></div>

**Step 2**: SWEe! will let you know whether there were any flashcards matching the keyword(s) in the *Result Display*, similar to number 2 in the picture below.

**Step 3**: You can see the matching flashcards in the list view, similar to number 3 in the picture below.

![Find Step 2 & 3](images/ug/ug_find_step23.png)

<div style="page-break-after: always;"></div>

### View help : `help`

If you forget how to use the app or have some things you are unsure about, fear not! You can use our help function which will lead you to our user guide.

Format: `help`

**Steps to use the help function**

**Step 1**: Type `help` in the command box and press Enter.

![Help step 1](images/ug/ug_help_step_1.png)

**Step 2**: A new window will pop out with a link.

![Help step 2](images/ug/ug_help_step_2.png)

**Step 3**: Simply press "Copy URL" then paste the link in your favourite browser, and you will be brought to our user guide website.



### List all flashcards : `list`

Want to see all of your flashcards? This is the command for you! 

<div markdown="span" class="alert alert-primary">

:bulb: **Tip:** This command would be especially helpful in helping you to see your original list of flashcards after executing [filter](#filter-for-flashcards---filter) or [find](#find-flashcards--find) commands!

</div> 

Format: `list`

<div style="page-break-after: always;"></div>

**Steps for listing flashcards**:

**Step 1**: Type `list` in the *Command Box* and press *Enter*. 

![List Step 1](images/ug/ug_list_step1.png)

<div style="page-break-after: always;"></div>

**Step 2**: The *Result Display* will display the message "Listed all flashcards" 

**Step 3**: All the flashcards are now displayed in the scrollable list view! Scroll down to see all of your flashcards!

![List Step 2 & 3](images/ug/ug_list_step23.png)

<div style="page-break-after: always;"></div>

### Review flashcards: `review`

Want to study your flashcards? Our review mode lets you easily navigate freely between flashcards to study them so that you can ace your next exam!

Format: `review`

Typing `review` and pressing Enter will put you in review mode and allows you to review the current displayed flashcard list.
<br><br>
So what is review mode? Upon entering review mode, you can no longer input commands to the command box. However, the following keyboard input will now be recognised:

* `↓ key` shows answer and notes of the current flashcard  
* `↑ key` hides answer and notes of the current flashcard  
* `→ key` moves on to the next flashcard (if there is a next flashcard)
* `← key` moves to the previous flashcard (if there is a previous flashcard)
* `q` quits review mode

<div markdown="span" class="alert alert-primary">:memo: Note:
The review and success frequency of a flashcard is <b>not affected</b> by review mode.
</div>
<br>

<div style="page-break-after: always;"></div>

**Steps for entering review mode**:

**Step 1**: We want to enter review mode to review our flashcards. Type the command `review` and press Enter.

![Review step 1](images/ug/ug_review_step1_edited.png)

**Step 2**: We are brought into review mode. The instructions on how to navigate review mode will be shown at the top.

![Review step 2](images/ug/ug_review_step2_edited.png)

<div style="page-break-after: always;"></div>

**Step 3**: In this example, we will demonstrate the behaviour of the `↓ key`. Upon pressing the `↓ key`, the answer of the flashcard is shown.

![Review step 3](images/ug/ug_review_step3_edited.png)

**Step 4**: Now, let's move onto the next flashcard. We just need to press the `→ key`

![Review step 4](images/ug/ug_review_step4.png)

<br>

To summarise, when you are in review mode, use the `↓ key` and `↑ key` to toggle showing the flashcard’s answer and notes. Use the `→ key` and `← key` to move between flashcards. Use the `q key` to quit review mode.

<div style="page-break-after: always;"></div>

### Quiz flashcards: `quiz`

Quizzes the current list of flashcards. This puts the user in quiz mode and the user can no longer input commands to the textbox.

Format: `quiz`

Upon entering quiz mode, the following user input will be recognised:
* `↓ key` shows answer and notes of the current flashcard  
* `q` quits quiz mode
* `y` This input will only be recognised after the `↓ key` is pressed. `y` is a feedback to indicate a correct answer. 
* `n` This input will only be recognised after the `↓ key` is pressed. `n` is a feedback to indicate an incorrect answer. 

Upon pressing the `↓ key`, the user will be prompted if they got the answer correct. The user can then press 
`y` to feedback that they got the correct answer or `n` to feedback that they got an incorrect answer.  

The quiz mode works in conjunction with the [statistics](#view-the-statistics-of-flashcard--stats) feature. Quiz attempts are recorded and information about the success frequency can be displayed using the [statistics](#view-the-statistics-of-flashcard--stats) feature.
* Pressing `y` will increase the review and success frequency of the flashcard.
* Pressing `n` will increase the review frequency of the flashcard.

<div markdown="span" class="alert alert-primary">:memo: Note: Once the user presses <code>y</code> or <code>n</code>, the review and success frequency of the flashcard is updated accordingly even if the user quits the quiz prematurely.
</div>
<br>

<div style="page-break-after: always;"></div>

**Steps for entering quiz mode**:

**Step 1**: We want to enter quiz mode to test ourselves on the current list of flashcards. Type the command `quiz` and press Enter.

![filedirectory](images/ug/ug_quiz_step1.PNG)

**Step 2**: We are brought into quiz mode. The instructions on how to navigate quiz mode will be shown at the top.

![filedirectory](images/ug/ug_quiz_step2.PNG)

<div style="page-break-after: always;"></div>

**Step 3**: In this example, we will demonstrate the behaviour of the `↓ key`. Upon pressing the `↓ key`, we will be prompted if we got the answer correct.

![filedirectory](images/ug/ug_quiz_step3.PNG)

**Step 4**: We got this answer correct so we will press `y`. This will automatically bring us to the next flashcard.

![filedirectory](images/ug/ug_quiz_step4.PNG)

<div style="page-break-after: always;"></div>

### Sort all flashcards : `sort`

Want to get an overview of how skilled you are at answering the flashcards? Our sort command is here to help you, with two important criteria that you can sort your flashcards by, namely the review frequency and success rate of your flashcards!

Format: `sort <success|reviewed> <-a|-d>`

* Specifying `-a` means sorting by the criteria in ascending order.
* Specifying `-d` means sorting by the criteria in descending order.

Examples: 
* `sort success -a` sorts the flashcards according to success rate in ascending order
* `sort success -d` sorts the flashcards according to success rate in descending order
* `sort reviewed -a` sorts the flashcards according to review frequency in ascending order
* `sort reviewed -d` sorts the flashcards according to review frequency in descending order

**Steps for sorting flashcards**:

**Step 1**: In this example, we want to sort the flashcards according to success rate in an ascending order. Type `sort success -a` into the command box and press Enter

![filedirectory](images/ug/ug_sort_step1.png)
<div style="page-break-after: always;"></div>

**Step 2**: The result display will show a message telling you that the flashcards have been sorted according to success rate in ascending order

**Step 3**: The list view will show the newly sorted list of flashcards according to the criteria

![filedirectory](images/ug/ug_sort_step2.png)

<div style="page-break-after: always;"></div>

### View a flashcard  : `view`

Want to view a flashcard in all its detail? The view command allows you to do just that! You will be able to see the full question on the flashcard and the diagram (if present) of the flashcard. Optionally, you can also choose to see the answer and notes (if present) of the flashcard.

Format: `view INDEX [-a]`

* If `-a` is specified, the answer and notes of the flashcard will be shown too.

Examples:
* `view 1` shows the flashcard at index 1 on the view pane **without** answer and notes.
* `view 1 -a` shows the flashcard at index 1 on the view pane **with** answer and notes.

<div markdown="span" class="alert alert-primary">:memo: Note: Once another command is executed, the view pane will be returned to a blank state even if the shown
flashcard was not modified/deleted.
</div>
<br>

<div style="page-break-after: always;"></div>

**Steps for viewing a specific flashcard**:

**Step 1**: Locate the flashcard you wish to view. In this example, we want to view the flashcard at index 3. Type the command `view 3` and press Enter.

![filedirectory](images/ug/ug_view_step1_edited.png)

**Step 2**: We will be presented with a "snapshot" of the flashcard at index 3 in the view pane.

![filedirectory](images/ug/ug_view_step2_edited.png)

<div style="page-break-after: always;"></div>

**Step 3**: Now lets say we also want to view the answer and notes (if present) of this flashcard. Type the command `view 3 -a` and press Enter.

![filedirectory](images/ug/ug_view_step3_edited.png)

**Step 4**: The answer of the flashcard is displayed on the view pane as well.

![filedirectory](images/ug/ug_view_step4_edited.png)

<div style="page-break-after: always;"></div>

### View the statistics of flashcard : `stats`

View the statistics of a flashcard.

Format: `stats INDEX`

* Shows the statistics of the flashcard at the specified `INDEX`. The `INDEX` refers to the index number shown in the displayed flashcard list.
* `INDEX` must be a positive integer **greater than 0**. eg. 1, 2, 3, …

Example:
* `stats 1` shows the statistics of the 1st flashcard (in the displayed flashcard list) on the view pane.

The statistics feature works in conjunction with the [quiz](#quiz-flashcards-quiz) feature.

The following information will be displayed on the view pane:
* Question of the flashcard (may be truncated for brevity).
* Reviewed count of the flashcard.
* Correct count of the flashcard.
* Pie chart to show the graphical representation of correct attempts vs wrong attempts in quiz mode of the flashcard. (No pie chart will be shown if the flashcard has not been reviewed.)

<div markdown="span" class="alert alert-primary">:memo: Note: Once another command is executed, the view pane containing the statistics will be returned to a blank state even if the shown
flashcard was not modified/deleted.
</div>
<br>

<div style="page-break-after: always;"></div>

**Steps for viewing the statistics of a specific flashcard**:

**Step 1**: Locate the flashcard you wish to view the statistics of. In this example, we want to view the statistics of the flashcard at index 1. Type the command `stats 1` and press Enter.

![filedirectory](images/ug/ug_stats_step1.PNG)

**Step 2**: The statistics of the flashcard at index 1 will be displayed in the view pane.

![filedirectory](images/ug/ug_stats_step2.PNG)

<div style="page-break-after: always;"></div>

### Exit the program : `exit`

Exits the program.

Format: `exit`

### Saving the data

Flashcards data are saved in the hard disk automatically after any command that changes the data. There is no need to save manually.

--------------------------------------------------------------------------------------------------------------------

<div style="page-break-after: always;"></div>

## FAQ

**Q**: What does it mean if some action is **not supported**?<br>
**A**: It means that our app is not intended to allow said action to work although it may work under certain circumstances.
If you still want to perform the action, do take note that you may face unintended or unexplained behaviour.

**Q**: What is the difference between review mode and quiz mode?<br>
**A**: Review mode is like a sandbox mode where you can move back and forth between flashcards. In quiz mode, you can only go forward. Also, quiz mode asks you for feedback and keeps track of statistics but review mode doesn't.

**Q**: Are success frequency and correct count of a flashcard the same thing?<br>
**A**: Yes. They both refer to how many times you answered with `y` in quiz mode for the flashcard.

**Q**: Why doesn't review mode affect review frequency/count of a flashcard?<br>
**A**: We know the naming may be a little bit confusing but just keep in mind that review mode does **not** affect the statistics (success, review frequency) of a flashcard. Only quiz mode does!

**Q**: What is the success rate of a flashcard?<br>
**A**: Success rate of a flashcard is measured by `(success frequency) / (review frequency) x 100%`. If a flashcard has a review frequency of 0, then its success rate will be 0%.

--------------------------------------------------------------------------------------------------------------------

<div style="page-break-after: always;"></div>

## Command summary

Action | Format, Examples
--------|------------------
**Add** | `add q/QUESTION a/ANSWER [c/CATEGORY] [n/NOTE] [r/RATING] [d/DIAGRAM] [t/TAG]...` <br> eg. `add q/What does OOP stand for? a/Object Oriented Programming c/General n/Important question! d/images/diagram.jpeg`
**Clear** | `clear`
**Delete** | `delete INDEX` <br> eg. `delete 3`
**Edit** | `edit INDEX [q/QUESTION] [a/ANSWER] [c/CATEGORY] [n/NOTE] [r/RATING] [d/DIAGRAM] [t/TAG]...` <br> eg. `edit 3 q/What does OOP stand for? a/Object Oriented Programming`
**Filter** | <code>filter [c/CATEGORY] [r/RATING] [f/<yes&#124;no>] [t/TAG]...</code> <br> eg. `filter t/examinable r/3`
**Fav** | `fav INDEX` <br> eg. `fav 1`
**Unfav** | `unfav INDEX` <br> eg. `unfav 1`
**Find** | `find KEYWORD [KEYWORD]...` <br>  eg. `find general important`
**Help** | `help`
**List** | `list`
**Review** | `review`
**Quiz** | `quiz`
**Sort** | <code>sort <success&#124;reviewed> <-a&#124;-d></code> <br> eg. `sort success -a`
**View** | `view INDEX [-a]` <br> eg. `view 1`
**Stats** | `stats INDEX` <br> eg. `stats 3`
**Exit** | `exit`

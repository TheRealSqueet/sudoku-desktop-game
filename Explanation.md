## Getting the System Running 

  

#### Environment:

-   openjdk version "21.0.10" 2026-01-20 LTS
-   IDE: VsCode
-   OS: Windows

#### Steps to get the system running:

First I needed to install maven as the package manager, realized I didn't have JDK so installed that as well.

Next had to update the versions of jooq in the dependency files and remove one breaking dep.

After fixing the deps the system runs.

#### Any build errors encountered:

Maven initial installation and build didn't want to run as there was a version mismatch issue. 

I realigned the versions and removed a breaking dep as previously stated which fixed the build issues.

breaking dep was: `jooq-codegen-maven`

#### How I diagnosed and resolved the issues:

The stacktrace gave a fairly straightforward explanation in the console when the errors ran.

I was able to paste the errors directly into chatGPT and ask it to direct me to the deps to fix to avoid digging through the log.

Three attempts later and manually implementing the change myself to avoid chatGPT's complimentary restructures and the issue was resolved.

#### My overall approach:

Attempt to install and build to see which errors would appear, then paste the errors into AI for a quick summary and implement recommended changes.

#### Evidence:

successful build photo:

![successBuild](successBuild.png) 

successful running of the application photo:

![successRun](successRun.png)   

  

  

  

## Understanding the System

  

#### What problem does it solve?

The system is a video game. It's a suduko simulator with local persistence enabled by SQLite so you can continue matches that are partway complete later. It's simply for entertainment.

#### What are its major features?

-   SQLite persistence allowing you to pick up where you leave off
-   Multiple language support (Polish and English)
-   A clickable user interface with a simple GUI

#### How does a user interact with it?

Upon installing the dependencies and building the project the user runs `mvn javafx:run -pl View` in their CLI as per the original application README to run the game.

Then the game's GUI pops up and the user can click through it to start/load a game and play, save, etc.

#### Evidence

I changed the UI elements on the main menu to include some silly words I find funny like "sigma" and "EPIC" by editing the english language properties files in the view/bundles folder.

Here's what it looks like now.

![changedUIText](changedUIText.png) 

  

  

## Architecture Exploration and Reflection
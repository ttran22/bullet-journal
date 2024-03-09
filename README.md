[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/x6ckGcN8)
# 3500 PA05 Project Repo

[PA Write Up](https://markefontenot.notion.site/PA-05-8263d28a81a7473d8372c6579abd6481)

# Running .jar
run oodle.jar(1) from run configurations, or right click oodle.jar in main to run
[oodle.jar](src/main/oodle.jar)


![OODleMainPage.png](sample-images%2FOODleMainPage.png)
![OODleNewEvent.png](sample-images%2FOODleNewEvent.png)
![OODlePage.png](sample-images%2FOODlePage.png)

# SOLID

## Single Responsibility
Multiple classes, for example, a controller and gui for each of the scenes - splash page, welcome screen, bullet journal.
Within our model, logic is seperated into classes. For example, Events are seperate from Tasks as they have different 
behavior and functionality.

## Open/Closed
Our controller and viewer implement interfaces that make them extendable. However, the functionality of the classes that 
implement these interfaces are contained within private methods, making them closed for modification. For example, the 
only public method in our JournalControllerImpl is run(), which is implemented because of the interface.

## Liskov-Subsitution
The scene on the stage is switched by using different view classes. For example, GuiWelcomeView vs GuiSplashView. They
all have a common load method so any view class can be used wherever the interface is.

## Interface Segregation
We had considered Event and Task implementing the same interface. However, we realized they have very little common
behavior. For example, Events do not have descriptions, thus we did not need to implement methods for parsing links 
or searching for keywords.

## Dependency Inversion
None of our classes which implement common interfaces depend on the behavior of other classes that implement the same 
interface. For example, the controller interface only promises a common run() method, but does gaurantee exactly how 
they will run.

# Future Features
The easiest additional feature we could implement would be the Weekly Overview. We already have a task bar of all tasks 
within a week, as well as a progress bar. We would only need to additionally keep track of all events within a a week, 
and then have a shared menu for all this data.

# UI Lab #1: Light Bulbs

![TimTheCook](images/cook_hero.png)

> Let your joy be in your journey - not in some distant goal. ~[Tim Cook](https://en.wikipedia.org/wiki/Tim_Cook)

## Learning Objectives - The student should be able to...

* Complete this lab, solidifying what it is they know about this unit and ones prior.

## What the student can do at this point 

* Has a general overview of Xcode and is able to create a new project.
* Knows where to locate the testing file within Xcode.
* Knows how to navigate to Interface Builder.
* Knows what a storyboard file is.
* Has a brief overview of what the Object Library is.
* Can drag a View Controller onto the canvas.
* Can locate and drag items from the Object Library.
* Can locate the Attributes Inspector and change the Background color of Views
* They know how to connect the `ViewController.swift` file and understand its view life cycle.
* Can hook up IBOutlets and IBActions.
* Understands UIKit.

## Light Bulbs

As you've been working through these lessons, a few light bulbs have no dealt turned on in your head as you've connected the dots of Swift programming. To celebrate, why not make an application where you can turn a light bulb a different color?

Specifically, your task is to create an app with this UI:

![LightBulb user interface](http://i.imgur.com/zydvVvj.png)

Pretty simple, right? Can you tell what user interface elements it consists of?

There are only two user interface elements in this application:

1. A view that draws a colored light bulb.
2. A segmented control that allows the user to select a color.

When the user selects a different color, the light bulb's hue should change. Easy, right? Here's what it looks like when the user presses **Green**:

![LightBulb: Green Edition](http://i.imgur.com/m5aboWl.png)

### Using Code

Part of being a competent Swift programmer is being able to use and modify an existing code base to accomplish your task. To reinforce this idea, part of this app has been provided for you. Open up `LightBulb/LightBulb.xcodeproj` in Xcode to see what has been given to you.

Let's go over the parts of the app that are already present in that project.

Open up `Main.storyboard`. You'll notice that a standard view controller has already been created for you. Notice, too, that the light bulb view has also been placed. However, it has _not_ been connected to anything yet—it's up to you to hook it up to the view controller's code properly.

Now open up `ViewController.swift` (you can open it up in an Assistant Editor from Interface Builder if you want). Parts of this file have already been filled in for you, too. It already has an IB action named `colorSelected(_:)`, but that IB action is not hooked up to anything. It also has a `UIView` outlet called `lightBulb`, but that has not been hooked up to anything, either.

You have also been provided with a method for turning strings into colors. For example, you can call `"red".color` to get a red color. `"blue".color`, `"yellow".color`, and `"green".color` are also allowed. This should help you easily create `UIColor` objects and use them in the existing methods.

You can also call `color` on segmented control objects. For example, given a segmented control called `sender` (such as the one passed to `colorSelected(_:`), you can call `sender.color` to get the color associated with it.

Finally, there are three method stubs that have `TODO` markers indicating code that _you_ have to write: `viewDidLoad()`, `changeColor(to:)`, and `colorSelected(_:)`.

Now, on to your tasks.

### Your Tasks

If you complete the following steps, you should end up with a properly working app:

1. Hook up the `lightBulb` IB outlet in `ViewController.swift` with the light bulb view in `Main.storyboard`.
2. Add a segmented control underneath the lightbulb.
	* By default, a segmented control only has 2 buttons. Yours needs to have 4. Do you know how you can change that? (If you guessed "in the Attributes Inspector", you'd be correct!)
	* The individual parts of a segmented control also have default names. Try to figure out on your own how you can change those names. (Hint: Look for a section in the Attributes Inspector called **Segment**. It is a popup menu that should list all the parts of your segmented control. You'll want to change an attribute called **Title** for each segment part.)
3. Hook up the segmented control to the `colorSelected(_:)` IB action in `ViewController.swift`.
4. Modify the `colorSelected(_:)` method where shown. It should change the background color of the `lightBulb` view to the chosen color.
	* Doing this might be a bit tricky. Notice that there is a `print` statement above the part of this method that you need to modify. That `print` statement is a hint as to how you can figure out which segment the user selected. Remember: You can get help using Xcode's documentation.
	* The selected part of the segmented control will be returned as an `Int`. Remember: You have already been provided with a method that can turn an `Int` into a color!
5. Modify the `changeColor(to:)` method to change the background color of the `lightBulb` view.
6. Finally, modify `viewDidLoad()` to set the initial color of the light bulb to red.
	* Remember: You have two methods to help you. One is `colorFromString(_:)`, which can take a string like "red" or "blue" and return a color.
	* You also have your trusty `changeColor(to:)` method, which can change the light bulb's color to any color you want.

Have at it! This is definitely one of the most challenging labs you've had so far, but you've been provided a lot of helpful pieces to get you started, and covered all the material you need to know in previous lessons, so you should do great with it!

<a href='https://learn.co/lessons/UILab01' data-visibility='hidden'>View this lesson on Learn.co</a>

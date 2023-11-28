# Library Information
The library that I selected was the racket/gui/base library. Racket has had the abiility for users to make GUI's since its creation in 1995, but it was not untill 2010 that this functionality was rebuilt, and the racket/gui/base library was created [[ref]](https://blog.racket-lang.org/2010/12/rebuilding-rackets-graphics-layer.html). This library allows for the creation of graphical user interfaces in Racket with a myriad of different widgets such as buttons, radio buttons, sliders and gauges, everthing that someone might need when creating a user interface [[ref]](https://docs.racket-lang.org/gui/Widget_Gallery.html). To use this library, it is helpful if you have seen object oriented programming in Racket before, as each widget is represented as a separate class. 

The first thing that is required to make a GUI in Racket is a frame. If you are familliar with JavaFX, the frame is Racket's version of the scene class [[ref]](https://docs.oracle.com/javase/8/javafx/api/javafx/scene/Scene.html). The frame is the window that appears when you run the program, and it holds all other containers and widgets that we will add to the program. To display it when the program runs, we use `(send frame show #t)`, where frame is the name of the frame that you created, and #t tells the program to show the frame. A #f would tell the program to hide the frame, which can be useful if there are multiple views in the program [[ref]](https://www.techopedia.com/definition/27453/view-mvc-aspnet). With the frame declared, any other widgets can be created and added to it through the parent parameter, which is present in all other widgets.

# Library Functionalities
The main draw of this library are the widgets, as they make up the entirety of the program. Two of the most basic widgets that tend to be used by most GUI's are the message, which is similar to the Label class in JavaFX [[ref]](https://docs.oracle.com/javase/8/javafx/api/javafx/scene/control/Label.html?external_link=true), and button widgets. Below is code to create both a message and a button in a frame.
```
(require racket/gui/base)
(define frame(new frame% [label "Example"]))

(new message%
     [parent frame]
     [label "Hello World"])

(new button%
      [parent frame]
      [label "Press Me!"]
      [callback function])

(send frame show #t)
```
In this example, a message and a button are added to the frame. The message has two parameters, parent and label. Parent is just which container to put the message in, which is frame in this example, and label is just what is displayed by the message. Button has those same parameters, but it also has callback. the callback parameter passes the function that will be called when the button is pressed, and the function must pass two parameters, one for the button that was pressed and one for the specific event that was created when the button was pressed. 

There are also container widgets like vertical-pane and horizontal-pane which can be added to the frame, and can act as the parent for other widgets. Below is how a pane would be defined and a message added to it:
```
(define pane (new pane% [parent frame]))

(new message%
      [parent pane]
      [label "Hello World"])
```
In this example, the message is being added to the pane rather than the frame. This can allow for a visual seperation or grouping of widgets in the frame.

# Personal Reflection
I selected this package because I have been enjoying Racket more as I deepen my understanding, so I wanted to work with it more in order to increase my proficiency with it. Also, I am in the class Building UI, which recently had a project that focused on different GUI tools other than JavaFX so I was curious as to how Racket handled creating GUI's. Learning this library did not really influence my learning of Racket since it included a lot of stuff that I had already been exposed to. The only thing that it influenced was that I am more interested in looking at the different functions included with pre-built classes, and using inheritance to create specific versions of classes to suit my needs. Overall, my experience with the library was good. The documentation was easy to follow and the widgets themselves were easy to create and use. I would recommend this package to someone who is looking to learn how to make GUI's, as the display heirarchy is very visible and easy to use with each widget having the parent parameter. Additionally, the code is very clean and concise, which means intro users will not be scared off by its complexity. I would use this library again if I needed to create a simple GUI, because even though I am more familliar with Java the simplicity of Racket's GUI tools would make whatever I was looking to do much easier. If I were creating a more complex program, a different GUI toolkit may be better since Racket is lacking in some aspects where a toolkit like JavaFX has better functionality for the complex stuff. 

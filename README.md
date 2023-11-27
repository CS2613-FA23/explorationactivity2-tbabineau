[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/kCrKdl4V)
# ExplorationActivity2

# Library Information
The sample program demonstrates the [racket/gui language](https://docs.racket-lang.org/gui/) which combines the racket/gui/base library and the racket/draw library, which allows us to create dynamic graphical user interfaces in Racket.

# How to run the Program
1. Install Racket. The installer for the Racket IDE "Dr. Racket" can be found [here](https://racket-lang.org/download/). Make sure that you download the correct installer for your operating system. Once downloaded, run the installer and follow the steps to get Racket installed on your machine.
2. Download the program from this repository. This can be done by clicking the green "Code" button in the top right of the screen, and selecting "Download ZIP" from the menu.
3. Un-zip the program. Navigate to your downloads folder and find the zipped folder that was just downloaded, right click on the folder and select "Extract all" from the menu.
4. Open the program. Do this by double-clicking on the file "RPS.rkt" found within the folder, this will open it in Dr. Racket.
5. Run the program. To do this, press the green play button in the top right of the Dr. Racket window, this will run the program and open it in a new window.

Instructions and tips on how to use the program can be found below, in the "Sample Input and Output" section.

# What Purpose does RPS.rkt Serve?
RPS.rkt demonstrates the different functionalities and widgets included in the racket/gui language as a simple rock paper scissors game.

# Sample Input and Output
When the program is first started, a window will appear that looks like this:

![RPS_Startup](https://github.com/CS2613-FA23/explorationactivity2-tbabineau/assets/125689414/e93daa54-be58-4e5e-8054-4f159c784c23)

Clicking on the drop down menu will give you three options: rock, paper or scissors.

![RPS_Dropdown](https://github.com/CS2613-FA23/explorationactivity2-tbabineau/assets/125689414/83675261-2511-4b2f-b831-5076c1e13910)

Select whichever you want to use, and press the button labeled shoot. The program will randomly select one of the options and determine who won. Once either player is at 5 points, the shoot button will be removed to ensure that no more input from the user can be received, and the program will wait for two seconds to ensure that the player has seen the last game message

![RPS_GameEnd](https://github.com/CS2613-FA23/explorationactivity2-tbabineau/assets/125689414/10e531bd-e0a7-416c-9cfd-d7b9bed6594b)

After waiting, it will display this game over screen:

![RPS_TryAgain](https://github.com/CS2613-FA23/explorationactivity2-tbabineau/assets/125689414/18aa4335-893f-46ee-8912-866b12c2ec6a)

The score displayed is how many games have been won by either you or the computer. If you press the play again button, you will be returned to the original screen that was shown when the program was first opened. To close the program at any time, press the red button at the top of the screen, it will be the same you use to close any other window in your operating system

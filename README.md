# Exercise-01c-Export-from-Twine

Exercise for MSCH-C220

This exercise will set up Twine to be able to export a version of an interactive fiction game that could be used in a Python game engine.

Begin by Forking this repository. Check that it has been forked successfully; the repository should now read [your username]/Exercise-01c-Export-from-Twine

Edit the LICENSE and replace BL-MSCH-C220-F22 with your full name. Commit your changes.

Press the green "Code" button and select "Open in GitHub Desktop". Allow the browser to open (or install) GitHub Desktop. Once GitHub Desktop has loaded, you should see a window labeled "Clone a Repository" asking you for a Local Path on your computer where the project should be copied. Choose a location where you will keep the repositories for this class (a C220 folder off your Desktop would be fine). Make sure the Local Path ends with "Exercise-01c-Export-from-Twine" and then press the "Clone" button. GitHub Desktop will now download a copy of the repository to the location you indicated.

Open Twine. In the Twine menu at the top of the window, select "Story Format". You should see a list of possible story formats for Twine. In the top left corner is a button labeled "+ Add". Select that now.

The resulting pop-up window should read "To add a story format, enter its address below." Enter `https://cdn.githubraw.com/BL-MSCH-C220-F22/JTwine-to-JSON/main/format.js` and press the green "+ Add" button.

Next, in the Library menu, select the Import button. In the resulting popup, navigate to the exercise folder on your computer and select Zork.html. Select the "Zork" story, and then press "Import Selected Files". If you open the resulting story, you will see our familiar story (from an earlier exercise).

If you press the Build->Play button, you will see the (also) familiar representation of your game in a web browser. By default, Twine uses the Harlowe 3.3.1, playable story format, with its black background and link-based navigation. We will now export the story in a format that we can use in our game engine.

In the Story menu at the top of the window, select Details. You should now see a pop-up in the bottom-right corner. Change the "Story Format" and select "JTwine-To-JSON 0.1.0". If you now press Build->"Play", your browser will now display a single (JSON) file containing your story.

Now, we need to create the python code to read and display the newly formatted story.

Log into replit.com and Create a new Project. Select the Python template and name it Exercise-01c-Export-from-Twine. You will then be taken to a window with two panels. The left panel represents a file called main.py, and the right panel will be where you will run your program inside a Python interpreter.

Copy the following, and paste it at the top of the main.py window:

```
world = {}

if "story" in world and "passages" in world:
    print(world["story"])
    print()
    for passage in world["passages"]:
        print(passage["name"])
        print(passage["cleanText"])
        for link in passage["links"]:
            print(link["label"])
        print()
```


On the first line, you should now hava a statement that reads
```
world = {}
```
This statement initializes a variable (called world) as an empty dictionary. Select the {} and replace it with the contents of the browser window you copied previously. If you are successful, main.py should now be around 230 lines long instead of 15. *Be careful to only select the {}. When you are done, line 5 should still start world = {*.

The rest of main.py is quite simple. It will print out the name of the world, and then go through each of the passages and print out their relevant contents. Confirm you haven't made any mistakes by running main.py; press the green Run button in the top of the replit window. 

Like you did with Exercise-01b-Prompt-and-Response, create a new README.md file. The final state of the file should be as follows (replacing my information with yours). When you have finished editing, and then turn in the URL of the replit project (https://replit.com/@[username]/Exercise-01c-Export-from-Twine) on Canvas.

```
# Exercise-01c-Export-from-Twine

Exercise for MSCH-C220

A Python dictionary, describing an interactive fiction game, exported from Twine

## Implementation
Created using Twine 2 and exported with [JTwine-to-JSON](https://github.com/BL-MSCH-C220-S22/JTwine-to-JSON)

## References
[Zork, 1977 by Tim Anderson, Marc Blank, Dave Lebling, and Bruce Daniels](https://en.wikipedia.org/wiki/Zork)

## Future Development
None

## Created by
Jason Francis
```

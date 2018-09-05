# Quest System Pro Getting Started

<iframe width="560" height="315" src="https://www.youtube.com/embed/JfUYcqnx6dc" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

Once you've imported Quest System Pro into your project a new menu item will show up in your main menu bar.  **Tools / Quest System Pro / ***

## 1. Creating the managers

To initialize Quest System Pro you need to add the managers to your scene.

First, create a new object (name doesn't matter) and attach the following components to it:

-   QuestManager
-   DialogueManager
-   AudioManager
-   LocalizationManager

These 3 managers initialize the quest system and handle all events and so on.

## 2. Setting the databases

Next, you'll need to add the databases to the QuestManager. There are 3 databases

-   LanguageDatabase: Handles all language related things like messages that can be displayed to the user.
-   SettingsDatabase: Contains all settings for your project including UI prefabs used in the UI.
-   QuestDatabase: Contains all quests and achievements.

When you've added the QuestManager you'll see a new button at the bottom of the inspector "Generate and link databases". When you click this a folder selection window will show up. Once you've selected a location to save the new databases they'll auto. be generated and added to your managers object.

By default there are already databases available you can re-use. You can find these in the  **QuestSystemPro / Demos / Files / Databases**  folder.

## 3. Setting up the player

Assign the Player and QuestSystemPlayer components to your character objects.
If you're not using a player in your game (a puzzle game for example), just add the PlayerComponent to an empty object and ignore the range on all triggers.

## 4. Start creating quests

All done, you can now  [create quests](Quests/CreatingQuest.md)  and add them to your project. Remember that every scene that uses quests or dialogues needs to have the managers in that scene (you can use DontDestroyOnLoad).

## 5. Player & Triggers

Triggers are used to create objects in the world that can trigger a window or action. In Quest System Pro these triggers are used to start quests at NPC's, dialogues and more.

The triggers require 2 things to work, the actual trigger, and the player to calculate the distance to the trigger.  [More about triggers here.](Misc/Triggers.md)

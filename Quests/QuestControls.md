# Quest Controls

Quests can be managed through FSM's as well as your own code. Basic operations are very easy to use:

```csharp
myQuest.Activate(); // Activates the quest.
myQuest.Activate(false); // Activates the quest and keeps any progress that may have been set (for example, by a previous failed attempt to complete the quest).
myQuest.Cancel(); // Cancel the quest and stop it.
myQuest.ResetProgress(); // Reset this quest's progress. Note this does not cancel the quest, only reset it's progress.

var canComplete = myQuest.CanComplete();
if(canComplete.status)
{
    // We can complete the quest
}
else
{
    // We can't complete the quest
    Debug.Log(canComplete.message.ToString());
}
```
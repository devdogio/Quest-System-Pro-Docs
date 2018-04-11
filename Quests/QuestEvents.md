# Quest events

Quests have events that can be used to repaint UI or trigger your own code whenever it's state changes.

By default you have the following events at your disposal:

-   OnStatusChanged
-   OnTaskReachedTimeLimit
-   OnTaskProgressChanged
-   OnTaskStatusChanged

## Using the events

```csharp
myQuest.OnStatusChanged += (Quest quest) =>
{
    Debug.Log("The quest status = " + quest.status);
}
```
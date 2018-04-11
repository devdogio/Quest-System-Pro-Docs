# Quest Manager

The QuestManager is the component that manages all quests in the game. Besides just 'containing' the quests you can also use it's events to respond to ANY quest changing, rather than a specific quest changing. For example, you may want to know when any quest is accepted rather than a specific quest; This can be achieved with the QuestManager.

## Quest States

Getting quest states can be useful when you want to know which quests and achievements are active and completed.

```csharp
// This goes in your own code:
var states = QuestManager.instance.GetQuestStates(); // Get all quest states, these are the quests that have progress.
```

## Listening to all quest changes.

```csharp
// This goes in your own code:
QuestManager.instance.OnQuestStatusChanged += YourCallbackMethod1;
QuestManager.instance.OnQuestTaskReachedTimeLimit += YourCallbackMethod2;
QuestManager.instance.OnQuestTaskProgressChanged += YourCallbackMethod3;
QuestManager.instance.OnQuestTaskStatusChanged += YourCallbackMethod4;
```
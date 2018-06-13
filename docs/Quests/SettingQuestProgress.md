# Setting quest progress

You can set the quest progress at any time from anywhere in your application.

```csharp
myQuest.SetTaskProgress("taskKey", 1f); // Set operation, overrides any previous progress.
myQuest.ChangeTaskProgress("taskKey", 1f); // Adds / removes progress on the task. Useful for incremental steps.

// A useful method to see if the quest tasks are completed / have enough progress to complete the quest.
bool areTasksCompletable = myQuest.AreTasksProgressedSufficientlyToCompleteQuest();
```

Additionally you can also directly grab the task from the quest using:

```csharp
Task task = myQuest.GetTask("taskKey");
task.ChangeProgress(1f);
```
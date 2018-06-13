# Creating a custom quest time handler

The quest time handler handles the quest and its tasks time management. If a task's time has run out, it's up to the time handler to decide what has to happen next.

```csharp
[System.Serializable]
public class MyQuestTimeHandler : IQuestTimeHandler
{
	public bool failQuestWhenOutOfTime = true;
	public void OnTimerStarted(Task task)
	{

	}

	public void OnTimerUpdated(Task task)
	{
		
	}

	public void OnTimerStopped(Task task)
	{

	}

	public void OnReachedTimeLimit(Task task)
	{
		// The task has reached it's time limit, what should happen to the quest?
		task.Fail();

		if (failQuestWhenOutOfTime)
		{
			QuestLogger.LogVerbose("Quest cancelled because time limit was reached on required task (" + task.key + ").");
			task.owner.Cancel();
		}
	}
}
```
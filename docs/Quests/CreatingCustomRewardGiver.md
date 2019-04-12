# Creating a custom reward giver

Any class that implements the IRewardGiver interface can be selected inside the quest editor and is automatically serialized.

```csharp
[System.Serializable]
public class MyRewardGiver : IRewardGiver
{
	// Fields added here are serialized and can be assigned in the quest editor.

	public virtual RewardRowUI rewardUIPrefab
	{
		get { return QuestManager.instance.settingsDatabase.defaultRewardRowUI; } // Specify which UI prefab you'd like to use to show the reward. Note: The SettingsDatabase is a partial class, so you can add your own fields to it without overriding it - See: https://msdn.microsoft.com/en-us/library/wa80x488.aspx
	}

	public ConditionInfo CanGiveRewards(Quest quest)
	{
		return ConditionInfo.success;
	}

	public void GiveRewards(Quest quest)
	{
		// Give the player his/her reward. 
		
	}
}
```

Save the script outside of the QuestSystemPro folder to avoid loss of files with updates. Once you've saved the file, head back to the quest editor and add it to your reward givers.

![](Assets/RewardGivers.png)

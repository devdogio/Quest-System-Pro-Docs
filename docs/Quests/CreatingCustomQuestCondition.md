# Creating custom quest condition

Quests can be restricted using your own interface implementations. This allows you to, for example, create a quest level. If the player has to be at least level 10 to accept the quest you could create a quest condition like so:

```csharp
[System.Serializable]
class MyPlayerLevelCondition : IQuestCondition
{
    public int minPlayerLevel = 1;

    public ConditionInfo CanActivateQuest(Quest quest)
    {
        // Check if player is required level.

        return ConditionInfo.success;
    }

    public ConditionInfo CanCancelQuest(Quest quest)
    {
        return ConditionInfo.success;
    }

    public ConditionInfo CanDeclineQuest(Quest quest)
    {
        return ConditionInfo.success;
    }

    public ConditionInfo CanDiscoverQuest(Quest quest)
    {
        return CanActivateQuest(quest);
    }

    public ConditionInfo CanCompleteQuest(Quest quest)
    {
        return ConditionInfo.success;
    }
}
```

Once you've created and saved the script (outside of the QuestSystemPro folder) you can go back to the main quest editor and assign the quest condition to the quest. All public and private / protected serializable fields will be serialized and editable in the quest editor.
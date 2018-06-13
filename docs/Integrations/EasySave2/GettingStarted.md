# Easy Save 2 Integration

To use the easy save 2 saving and loading of quest and achievement progress you can attach the EasySave2SaveLoadManager to your managers objects.

!!! note
	Don't forget to remove the standard SaveLoadManager if you were using it.

![](Assets/EasySave2SaveLoadManager.png)

Add the following lines to your ES2Init.cs file

```csharp
ES2TypeManager.types[typeof(Devdog.QuestSystemPro.QuestsContainerSerializationModel)] = new ES2UserType_DevdogQuestSystemProQuestsContainerSerializationModel();
ES2TypeManager.types[typeof(Devdog.QuestSystemPro.QuestSerializationModel)] = new ES2UserType_DevdogQuestSystemProQuestSerializationModel();
ES2TypeManager.types[typeof(Devdog.QuestSystemPro.TaskSerializationModel)] = new ES2UserType_DevdogQuestSystemProTaskSerializationModel();
```

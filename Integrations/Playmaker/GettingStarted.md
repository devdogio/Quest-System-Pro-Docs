# Playmaker getting started

To relay events from the dialogue to PlayMaker you have to add the `DialoguePlayMakerEventProxy`. This script should be attached to the same object that contains the PlayMakerFSM component. It does not have to be linked specific dialogue reference.

## Events

| Event names | Event description | Value being set |
| --- | --- | --- |
| QUEST_SYSTEM_PRO/OnCurrentDialogueNodeChanged | A dialogue node has changed | QUEST_SYSTEM_PRO/Event_IntSets the index of the node that is now active. |
| QUEST_SYSTEM_PRO/OnCurrentDialogueChanged | A different dialogue has been activated. Note this can be null if the user stops using a dialogue! | QUEST_SYSTEM_PRO/Event_ObjectSets the dialogue object that is now active. |
| QUEST_SYSTEM_PRO/OnCurrentDialogueStatusChanged | The current dialogue's status just changed | QUEST_SYSTEM_PRO/Event_StringSets the DialogueStatus as a string |

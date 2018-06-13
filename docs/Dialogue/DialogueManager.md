# Dialogue Manager

The Dialogue Manager keeps track of the current dialogue, as well as some events that we can use to respond to these changing dialogues.

## Events

Here you can subscribe to the dialogue events. These events are 'global' events and are invoked when the current dialogue changed.

These same events also exist on the Dialogue itself, and can be used to listen to that specific dialogue instead.

```csharp
DialogueManager.instance.OnCurrentDialogueChanged += Callback;
DialogueManager.instance.OnCurrentDialogueNodeChanged += Callback1;
DialogueManager.instance.OnCurrentDialogueStatusChanged += Callback2;
```
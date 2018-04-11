# Custom Dialogue Nodes

The dialogue system is very dynamic, and because of this you can create your own nodes (and editors).

```csharp
[System.Serializable]
[Category("MyProject")]
public class MyNodeType : ActionNodeBase
{
	[ShowInNode]
	[Required]
	public int myInt = 3;

	public override void OnExecute(IDialogueOwner dialogueOwner​)
	{
		// Called when the node is executed.
		Finish(false); // Call finish when the node is finished, otherwise the dialogue won't continue to the next node.
	}

	public override NodeBase GetNextNode()
	{
		// Return the next node (using the edge we wish to use).
		return base.GetNextNode();
	}

	public override void OnExit()
	{
		// Called when the node is exited (useful for resource cleanup).
	}

	public override OnDialogueExit()
	{
		// Called on ALL nodes when the dialogue (owner) has been closed.
	}

	public override ValidationInfo Validate()
	{
		// Validate the state of the node.
		return new ValidationInfo(ValidationType.Error, "Wah! Something is wrong.");
	}
}
```

!!! note
	When referencing an asset, for example, a custom ScriptableObject type, use Asset<T> instead.

## Useful attributes:

**[ShowInNode]** can be used to show a field inside the node. If the attribute is not added it will only be shown in the sidebar.

**[Required]**  the field is required and can not be empty. Strings can't be emtpy and objects have to be assigned.

**[HideGroup]**  hides the grouping. Useful for arrays when you don't want to show the unfolding (Grouping).

## Custom node editors

```csharp
[CustomNodeEditor(typeof(MyNodeType))] // Set which node this editor belongs to.
public class MyNodeTypeEditor : DefaultNodeEditor // You must inherit from NodeEditorBase or any existing editor that inherits from it (such as DefaultNodeEditor)
{
	public override void Draw(bool drawContents)
	{
		DrawNodeState();

		// Draw specific node things
		// this.node is the node. You can cast this.node to your own type.

		DrawDebugView();
		DrawValidation();

		if (drawContents)
		{
			DrawEdgeConnectors();
			DrawReceivingEdgeConnectors();
		}
	}
}
```
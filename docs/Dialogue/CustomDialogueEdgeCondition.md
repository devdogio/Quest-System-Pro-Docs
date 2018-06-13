# Custom Dialogue Edge condition

Custom dialogue edges can be made to control the flow of the dialogue.

```csharp
public class MyEdgeCondition : IEdgeCondition
{
	public bool CanViewEndNode(Dialogue dialogue)
	{
		// Can the end node be viewed by the player?
		// When true is returned a player decision or reference to this node will be visible.
		// When false is returned a player decision or reference to this node will NOT be visible.

		// Optionally you can use: return CanUse(dialogue); to only show the edge when it can be used.
		return false;
	}

	public bool CanUse(Dialogue dialogue)
	{
		// Here you could check if your player has an item, is the right level etc.
		return false;
	}

	public ValidationInfo Validate(Dialogue dialogue)
	{
		return new ValidationInfo(ValidationType.Valid);
	}

	public string FormattedString()
	{
		// The string shown in the node editor.
		return "Fake condition";
	}
}
```
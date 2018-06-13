# Localization

All localization can be found in the Devdog.General.Localization namespace. And Devdog.General.Localization.Editors for all editor code.

## Built-in types

-   LocalizedString
-   LocalizedObject
-   LocalizedSprite
-   LocalizedTexture2D
-   LocalizedAudioClip

## Custom data types

You can also create your own localized object types (anything that inherits from UnityEngine.Object), but this does require you to implement your own editor, as unity doesn't support generic editors.

```csharp
[System.Serializable]  
public class LocalizedSprite : LocalizedObjectBase<Sprite>  
{  
	
	public LocalizedSprite()  
	{

	}

	public LocalizedSprite(string key)  
	: base(key)  
	{

	}  
}
```

And for the editor code:

```csharp
[CustomPropertyDrawer(typeof(LocalizedSprite), true)]  
public class LocalizedSpriteEditor : LocalizedObjectEditorBase<Sprite, LocalizedSprite>  
{ 
	
}
```

## Localization database

To set the current language through code you can call LocalizationManager.SetLanguage("en-GB"); With the localized database's language specifier.

LocalizationManager.SetLanguage("en-GB"); // To set the language to British english.

## Localized UI

The UI isn't repainted when the localization database changes, and a restart would be required (the current localization database would have to be set before any UI is displayed and rendered.
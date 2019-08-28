# CustomTutorials-2.1 :exclamation:
A framework that makes creating interactive tutorials. It handles both displaying the tutorials and saving the user progress in them.

### API Overview
|Name|Description|
|:--|:--|
| .RegisterTutorials(id, data) | Registers a new tutorial with the given ID. |
| .TriggerTutorial(id, index [,maxAdvance])| Advances a step in a given tutorial and unlocks progression up to `index`.  |
| .ResetTutorials(id) | Resets progression in a given tutorial. |
| .GetTutorials(id) | Returns `data` originally registered for a given tutorial. |

:warning: Note that all methods use a dot `.` syntax, instead of the more common `:` syntax.

### Usage Example
First of all, you must register the new tutorials for you addon:

``` 
Lib.RegisterTutorials("MyAddon", {
  savedvariable = "MyAddon_TutorialsSavedVariable",
  title = "MyAddons",
  {  -- This is tutorial #1
    text = "Hello",
    image = "SomeImage",
  },
  {  -- Tutorial #2
     text = "Bye",
  }
})
``` 

Finally, you need to tell CustomTutorials when you want the tutorials to be shown. If you provided the `savedvariable` argument, you won't have to worry about which ones the user has already seen neither to save that information. CustomTutorials will handle that for you:

``` 
  -- Shows up to tutorial #3 if the user has not seen it already
  MyAddon:TriggerTutorial(3)
``` 

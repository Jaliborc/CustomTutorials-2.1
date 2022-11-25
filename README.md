# CustomTutorials-2.1 :exclamation:
[![Patreon](http://img.shields.io/badge/news%20&%20rewards-patreon-ff4d42)](https://www.patreon.com/jaliborc)
[![Paypal](http://img.shields.io/badge/donate-paypal-1d3fe5)](https://www.paypal.me/jaliborc)
[![Discord](http://img.shields.io/badge/discuss-discord-5865F2)](https://bit.ly/discord-jaliborc)

A framework that makes creating interactive tutorials extremely simple. It handles both displaying the tutorials and saving the user progress in them.

## API Overview
|Name|Description|
|:--|:--|
| .RegisterTutorials(id, data) | Registers a new tutorial with the given ID. |
| .TriggerTutorial(id, index [,maxAdvance])| Advances a step in a given tutorial and unlocks progression up to `index`.  |
| .ResetTutorials(id) | Resets progression in a given tutorial. |
| .GetTutorials(id) | Returns `data` originally registered for a given tutorial. |
| :Embed(object) | Embeds the above methods into the given object. |

:warning: Note that, for legacy and embedding reasons, all methods except for `:Embed(object)` use a dot `.` syntax, instead of the more common `:` syntax.

## Usage Example
First of all, you must register the new tutorial for you addon:

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

Finally, you need to tell the library when you want the tutorial to be shown. If you provided the `savedvariable` argument, you won't have to worry about which panels the user has already seen neither to save that information. CustomTutorials will handle that for you:

```
  -- Shows up to panel #3 if the user has not seen it already
  MyAddon:TriggerTutorial(3)
```

## To Devs
If you use this library, please list it as one of your dependencies in the CurseForge admin system. It's a big help! :+1:

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

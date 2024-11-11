# Editor

## classes 
### TreeEditor
Use: 
Inherits from: EditorWindow 

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| ETE-01 | ability to zoom in and out using mouse scroller and move around the screen by click and drag with the mouse | 
| ETE-02 | ability to place nodes and move them around the screen | 
| ETE-03 | when opened the window will open to the tree node | 
| ETE-04 | When opened the tree nodes will remain linked and where they were when last accessed | 
| ETE-05 | will be created with a root node |
| ETE-06 | is opened when the tree file type is clicked from within editor | 

</details>

### TreeNodeVisual
Use: 
Inherits from: VisualElement

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| ETN-01 | Tree nodes can be added to the editor window and be moved around | 
| ETN-02 | Tree nodes can be linked to other tree nodes | 
| ETN-03 | The tree nodes change colour depending on their return value while behaviour tree is running it editor. Green = succeeded, Red = Failed, orange = Running, Purple = inactive. | 
| ETN-04 | Are linked to their correct implementation |
| ETN-05 | can remove links between children | 
| ETN-06 | when clicked its revealed valuables will show in the component view | 

</details>

### SaveButton
Use: 
Inherits from: UIToolkit.Button

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| ESB-01 | When pressed the file will update 
| ESB-02 | When the file is reopened in editor, it will return to the state it was closed on | 
| ESB-03 | when the file is reopened on a different PC or after running through git, it will return to the last state it was in | 

</details>

### ComponentView
Use: allows the user to view and edit revealed values in a node to adjust behaviour.

Inherits from: VisualElement 

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| ECW-01 | get and show all public and serialized fields from the component script | 
| ECW-02 | change serialized and public field values and have them apply to the object | 

</details>

### ContextMenu
Use: A menu that stores all the folders and tree nodes which can be added to the tree. When a node is clicked it will spawn in the window. 

Inherits from: VisualElement 

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| ECM-01 | When the Editor window is right clicked the menu will appear next to the mouse pointer 
| ECM-02 | all elements assigned to the context menu will appear in it including new elements | 
| ECM-03 | the user can add new elements and sub folders to the context menu through code | 
| ECM-04 | When an option is picked in the context menu it creates a tree node of the correct type | 

</details>

### RootNodeVisual
Use: 
Inherits from: TreeNodeVisual

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| ERN-01 | Is the node the tree starts from | 
| ERN-02 | Is created with the tree window |

</details>

### Decorator/ConditionVisual 
Use: 
Inherits from: TreeNodeVisual

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| EDC-01 | Can only accept one child | 
| EDC-02 | If another child is attempted to be added, it will supersede the previous and disconnect them | 

</details>

### ActionVisual 
Use: 
Inherits from: TreeNodeVisual

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| EAV-01 | can have no children | 

</details>

### ControlVisual
Use: 
Inherits from: TreeNodeVisual

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| ECV-01 | can have multiple children | 

</details>

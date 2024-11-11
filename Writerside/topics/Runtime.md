# Runtime

## Tree Manager 
Use: 
Inherits from: MonoBehaviour

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| TM-01 | Traverses the tree | 
| TM-02 | Loads the tree and tree data from its JSON file | 
| TM-03 | Allows you to pick which update it runs on | 

</details>

## Tree Data 
Use: holds pointers to other classes data so it can be used by the behaviour tree for quick references to conditions and data needed to perform actions. 

Inherits from: MonoBehaviour

## Tree Node
Use: tree node class that all tree node types inherit from. 

Inherits from: MonoBehaviour 

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| TN-01 | has a current activity which is constantly updated | 
| TN-02 | can hold, add and remove child TreeNodes | 
| TN-03 | is able to be aborted when needed | 
| TN-04 | has a run function that is ran by the tree manager | 

</details>

## Action 
Use: Action nodes are nodes which perform an action or task. 

Inherits from: TreeNode 

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| TNA-01 | can have no children | 

</details>

## Condition 
Use: condition nodes return true or false based on a Boolean condition being checked. If true it's child node will be performed. 

Inherits from: TreeNode 

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| TNC-01 | has a set priority which can cause aborts | 
| TNC-02 | will abort it's children when aborted due to higher priority condition being met | 

</details>

## Decorator 
Use: changes the return or behaviour of the nodes below it. 

Inherits from: TreeNode 

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| TND-01 | Can only have one child | 

</details>

### Inverter 
### Repeat Until Fail
### Timeout
### Cooldown 
### Loop X times 
### Force Fail 
### Force Success 
### Tag Cooldown 
### Conditional loop 

## ControlFlow node 
Use: Controls the traversal flow and dictates order of actions in its child nodes.

Inherits from: TreeNode 

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| TNF-01 | can have multiple children | 

</details>

### Sequence 
Use: performs actions in order from left to right, only succeeding if all actions succeed.
inherits from: ControlFlow 

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| TNF-02 | Goes through nodes from left to right | 
| TNF-03 | returns failure when one child fails | 
| TNF-04 | if one child fails, does not continue to other children | 
| TMF-05 | returns success when all children succeed | 

</details>

### Fallback 
Use: performs actions sequentially from left to right until all actions fail or one succeeds. 

Inherits from : ControlFlow 

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| TNF-06 | if one child fails, moves onto the next child | 
| TNF-07 | does not return fail until all children fail | 
| TNF-08 | returns success when one node succeeds and doesn't run later nodes | 
| TNF-09 | goes through children sequentially |

</details>

### Selector 
Use: picks a random action from it's children and performs it until all return failure or one returns success. 

Inherits from: ControlFlow 

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| TNF-06-8 | from Fallback node | 
| TNF-10 | goes through children in a random order | 

</details>

### Parallel 
Use: performs child nodes at the same time, return condition depends on percentage of tasks to succeed set up. 

Inherits from : ControlFlow 

<details>
<summary>Requirements</summary>

| Requirement code | Requirement | 
| ------ | ----- |
| TN-11 | all nodes run at the same time | 
| TN-12 | has a percentage of child nodes to fail/succeed in order to decide return | 

<details>

# Inventory

## data structures
Every possible inventory item is stored in a scriptable object with a custom data structure for the inventory items.

InventoryItem

{
* **Int ItemID** // the unique index assigned to an item that it can be accessed by.
* **String ItemName** // the name of the item in plain English that is shown to the player.
* **string Description** // a description for the use of the object shown to the user via the inventory page.
* **Image ItemImage** // image associated with the item that is shown on the inventory page. Possibly also shown to the user when they gain key items.
* **enum ItemType** //what type of item it is (recovery, material, key) for grouping in the inventory
* **enum OnUseFunction** // an enum that links to a function in the InventoryUseFunctions singleton. Each enum links to a different function or a different value pass in for a function that can then quickly be picked from the list, the function will be called from a switch in the classes OnUse() function.

}

Shops may then have a list of itemIDs with an associated buying and selling price for each. 
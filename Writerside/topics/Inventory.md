# Inventory

## How to use the inventory System
The inventory System has a scriptable object which holds all the items in the game. The scriptable inventory is a
polymorphic property drawer, a designer can choose from a dropdown list of types which inherit from InventoryItem, where
they can then edit the instance of the InventoryItem to have different values. This allows for items to be made with 
the same functionality to share a class. E.g. a small health potion (25% HP increase) and a medium health potion (50% 
health increase), would both be instances of the Health consumable class. 

To Create a new item type for new functionality, the item simply needs to inherit from InventoryItem, and implement an 
OnUse() function. For the sake of categorisation, currently Items also implement one of 5 interfaces: IConsumable, 
IMaterial, IAccessory, IWeapon or IKey, these all inherit from IItem and are used to differentiate between item types,
mostly for the sake of the UI. 

Any new item type created will automatically be added to the InventoryItem list in the scriptable object, as this list
is created via reflecting to see all classes which derive from InventoryItem. 

As InventoryItem classes increase, it may be worth looking into a way to also categorise the list itself by the interface 
it implements (deriving from IItem) to reduce the options in the list/ make it more manageable. 

## Inventory Item Types
All item types inherit from InventoryItem, which implements IItem which enforces the OnUse() function. Items are then 
split into types which are then used to categorise them by the UI. To categorise items the items class must inherit from
an interface for the item type which inherits from IItem. To implement a new item type, create a new interface which 
inherits from IItem. 

The base item types for the game which are currently planned include:
- Consumable
- Material 
- Accessory 
- Weapon 
- Key

## Consumable items 
If an item is Consumable, when a new Item type is created, its InventoryItem class must inherit from IConsumable.

**Consumable Item Types:**
- **Health Consumable** - Increases the players HP by a set percentage.
- **Magic Consumable** - Increases the players Seri points by a set percentage. 
- **Physical Attack Consumable** - Increases the players physical Attack by a multiplier for a set amount of time.
- **Physical Defense Consumable** - Increases the players Physical defense by a multiplier for a set amount of time.
- **Magic Attack Consumable** - Increases the players Magical Attack by a multiplier for a set amount of time.
- **Magic Defense Consumable** - Increase the players Magical Defense by a multiplier for a set amount of time. 
- **Agility Consumable** - Increase the players Agility by a multiplier for a set amount of time. 
- **Luck Consumable** - Increase the players luck (chance of landing a critical attack) for a set amount of time.

## Material items
If an item is a Material, when a new Item type is created, its InventoryItem class must inherit from IMaterial.

Material Items have a use function due to inheriting from IItem, but this functionality is not used, when materials are
used they are simply removed from the inventory. 

## Accessory items
If an item is an Accessory, when a new Item type is created, its InventoryItem class must inherit from IAccessory.

Accessories are items which can be equipped to the player that apply modifiers to different player stats. There is required changes to the player health script to enable this to happen which are planned. Unlike regular inventory items, there is a "weight" limit, or max stat multiplier on accessories which can be worn by the player at any given time. 

Some accessories may be breakable, this is undecided yet. 

**Accessory Item Types**

## Weapon items 
If an item is a Weapon, when a new Item type is created, its InventoryItem class must inherit from IWeapon.

Weapons types function essentially the same as Accessory items with extra functionality. 

## Key items
If an item is a Key Item, when a new Item type is created, its InventoryItem class must inherit from IKey.

## Classes 
### InventoryDataBaseGUI 
The class that controls what ScritptableInventories GUI looks like. 

### ObjectIDDrawer
Use [ObjectID] before a string variable to create a read only field which if empty will be automatically be filled with the string version of a Guid. 

### ConsumableItems
a script containing all the classes of consumable items. the same will be made for other item types when they're implemented. currently classes in here don't implement their intended functions but instead print that they have been used when OnUse() is called. 

### InventoryItem
inventory is the base class for all inventory items. items must inherit from this class in order to be added to the scritptable object and be added to the InventoryDatabaseGUI. 

### InventoryManager
Component class that allows things to be added and removed from the players inventory. 

### ItemInterfaces
interfaces related to item types are stored here. 

### ScriptableInventory
A list of all InventoryItem instances in the game. 

### InventoryItemButton
A UI class that when selected will send an event to the InventoryUIController to show the items details to the UI. 

### InventoryUIController
The class that controls the functionality of the Inventory UI in the main menu.


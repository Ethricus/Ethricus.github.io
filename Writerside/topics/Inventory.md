# Inventory

## Inventory Item Types
- Consumable
- Material 
- Accessory 
- Weapon 
- Key

## Inventory Item
All Inventory Items need to inherit from InventoryItem to be added to the inventory List. 
Inventory items implement IItem which has the function OnUse(). 
Other than operators, InventoryItem has 

## Consumable Item Classes
- Health Potion 
- Magic Potion 
- P.ATK Increase 
- P.DEF Increase 
- S.ATK Increase
- S.DEF Increase
- Agility Increase
- Luck Increase

## Inventory Classes
### InventoryManager.cs
Inherits from : MonoBehaviour

### Scriptable Inventory
Inherits from : ScriptableObject

### InventoryDatabaseGUI

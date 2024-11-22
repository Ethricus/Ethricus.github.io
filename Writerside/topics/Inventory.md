# Inventory

## Inventory Item Types
- Consumable
- Material 
- Accessory 
- Weapon 
- Key


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

All Inventory Items need to inherit from InventoryItem to be added to the inventory List. 
Inventory items implement IItem which has the function OnUse(). 

### interfaces 
- IItem

### InventoryItem.cs
inherits from: IItem

Variables:
+ ItemData : InventoryData {
        [ObjectID] public string ItemId;
        public string ItemName;
        public string ItemDescription;
        public UnityEngine.UI.Image ItemImage;
}

Methods: 
+ void OnUse()
+ bool Equals() 
+ bool GetHashCode()

Operators:
==
!=

[Serializable]
    public struct InventoryData
    {
        [ObjectID] public string ItemId;
        public string ItemName;
        public string ItemDescription;
        public UnityEngine.UI.Image ItemImage;
    }

### InventoryManager.cs
Inherits from : MonoBehaviour

### Scriptable Inventory
Inherits from : ScriptableObject

### InventoryDatabaseGUI

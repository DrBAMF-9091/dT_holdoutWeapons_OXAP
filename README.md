# dT_holdoutWeapons_OXAP
injects `ItemSlotType = EInventoryEquipmentSlot::Pistol` into template structs so inheriting weapons can be put in any slot

currently overwrites all OXA Prototype (another mod) templates and child objects 
these are in the .cfg files in
./Stalker2/Content/GameLite/GameData/ItemPrototypes/WeaponPrototypes

this is a bad way of doing this that I need to change

these:
./Stalker2/Content/GameLite/DLCGameData
./Stalker2/Content/GameLite/GameData/ItemPrototypes

both contain vanilla overwrites - they do the same thing, but vanilla weapons/variants are much simpler than OXAP so direct child injection works fine

OXAP has a different WeaponPrototype variant for every weapon's specific OXAP mod variations so there are alot

direct child injection is less practical for OXAP - trying to find out specifically how to inject changes somewhere in the middle of a reference lineage
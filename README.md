# dT_holdoutWeapons_OXAP
injects `ItemSlotType = EInventoryEquipmentSlot::Pistol` into weapon structs so they can be used in any slot

currently in two parts
Part 1:
currently overwrites all OXA Prototype (another mod) templates and child objects 
these are in the .cfg files in
./Stalker2/Content/GameLite/GameData/ItemPrototypes/WeaponPrototypes

the only thing it changes from the source files is the starting template's 
`ItemSlotType = EInventoryEquipmentSlot::` line
`EInventoryEquipmentSlot::` is changed from it's original setting to `Pistol` allowing any slot usage (something made for the pistol slot can be used in primaries as well, there is no functional difference between the slots besides restrictions on what can do in them)

this is a bad way of doing this that I need to change, I think it works since the template is redefined in full with the new value before the child objects are forced to reconstruct

including only template redefinitions doesn't work
Part 2:
these:
./Stalker2/Content/GameLite/DLCGameData
./Stalker2/Content/GameLite/GameData/ItemPrototypes

both contain vanilla patches - they do the same thing, but vanilla weapons/variants are much simpler than OXAP so just injecting the specific change works fine

OXAP has a different WeaponPrototype variant for every weapon's specific OXAP mod variations so there are alot

direct child injection is less practical for OXAP - trying to find out specifically how to inject changes somewhere in the middle of a reference lineage so they inherit further down
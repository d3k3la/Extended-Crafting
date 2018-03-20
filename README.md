DESCRIPTION:

These overwrites will allow you to use the welder, tool trollies and generators from 'Extended Base Mod' as requirements in your crafting recipes.
You will also be able to craft weapons with thanks to Novax for his ExileClient_util_item_getCraftingRecipes.sqf
The following distances are set for the EBM items to register as 'Found'
"Land_WeldingTrolley_01_F" < 5m
"Land_ToolTrolley_02_F" or "Land_ToolTrolley_01_F" < 5m
"Land_PortableGenerator_01_F" < 5m or "Land_DieselGroundPowerUnit_01_F" < 50m

INSTALLATION:

Create a folder in your mpmission folder called 'custom'
Copy the folder 'extendedCrafting' to the newly created 'custom' folder
Open your config.cpp and find 'class CfgExileCustomCode'

Add change it to the following 

class CfgExileCustomCode 
{
	ExileClient_object_item_craft = "custom\extendedCrafting\ExileClient_object_item_craft.sqf"; 
    ExileClient_gui_crafting_show = "custom\extendedCrafting\ExileClient_gui_crafting_show.sqf";
    ExileClient_util_item_getCraftingRecipes = "custom\extendedCrafting\ExileClient_util_item_getCraftingRecipes.sqf";
};

If you already have owverwrites for these files, then you will need to merge the changes manually

Re-pbo the mpmission folder and upload to your server

EXAMPLE RECIPE:

class gm6_lynx: Exile_AbstractCraftingRecipe
    {
            name = "GM6 Lynx 12.7mm";
            pictureItem = "srifle_GM6_F";
			requiresFire = 1;
			requiresWeld = 1; 
			requiresGen = 1;
			requiresToolTrolley = 1;
			//requiresConcreteMixer = true;
			requiredInteractionModelGroup = "AdvancedWorkBench";
            returnedItems[] =
            {
                    {1, "srifle_GM6_F"},
					{1, "5Rnd_127x108_Mag"}
            };
            tools[] =
            {
					"Exile_Item_Hammer",
					"Exile_Item_Grinder", 
					"Exile_Item_Pliers",
					"Exile_Item_Screwdriver"
            };
            components[] =
            {
                    {15, "Exile_Item_WeaponParts"},
					{2, "Exile_Item_MetalPole"},
					{4, "Exile_Item_MetalScrews"},
					{2, "Exile_Item_SprayCan_Black"},
					{1, "Exile_Item_MetalWire"},
					{2, "Exile_Item_Can_Empty"},
					{1, "Exile_Item_MetalBoard"}	
            };
			category = "Sniper Rifles";
    };

CUSTOMIZATION:
	
Add the following to your recipe and toggle on (1) and off with (0)

requiresWeld = 1; 
requiresGen = 1;
requiresToolTrolley = 1;
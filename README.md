# Freecad-Sheetmetal-kfactor-csv
Adding a more practical approach to the FreeCAD sheetmetal- unfolder

I had some time on holiday, and made a different approach by myself.

The unfolder looks for a csv-file on a specified place for each material. In there are the thickness and a given k-factor.
For example:

The folder is located in C:\ and is named "Freecad_Sheetmetal_Materials".
For trying this out, I gave the mod a parameter where the files are located:
Parameter-Editor - BaseApp - Preferences - Mod - Sheetmetal. I made a new parameter from string type named CSVMaterialFolder. 
The parameter text is (as our example) C:\Freecad_Sheetmetal_Materials

This is where the unfolder looks for the csv-files.

The file is built like this: (for example the S235.csv):
Thickness,KFactor
1.0,0.40
1.5,0.40
2.0,0.40
3.0,0.40
4.0,0.40
5.0,0.40
6.0,0.40
8.0,0.35
10.0,0.35
15.0,0.30

Inside the unfolder, you can either choose the known spreadsheet- technique, when there is a spreadsheet in the file.
Now, there are the csv-files for each material. 
When the csv-file is chosen, the k-factor for the thickness is automatically chosen and the length is automatically updated.

For safety, the actually chosen k-Factor is listed in the greyed out entry-field.

The changes I made are in:

SheetMetalKfactor.py
lookup.py
SheetMetalUnfoldCmd.py

I tested this with Freecad 1.1.0 and SheetMetal v0.8.24

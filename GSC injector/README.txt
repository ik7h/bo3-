To inject compiled GSC files:
1. Copy the GSC file to the "CompiledScripts" folder. If it is not there, run the .exe and it will be created.
2. Select it from the dropdown menu above the "Inject Script" button.
3. Click "Inject Script" when BO3 is open and if it is successful, it should say "Injection Successful!" in the output box.


Buttons Explanation:
- Folder Compile: Recursively compiles folders with .gsc files in them (useful for InfinityLoader project migration). It requires a main.gsc, and 
the main.gsc has to be the only file with #includes. If it is not ticked it will compile a single .gsc or .txt source file.

- Output function Hashes: This will output a .txt in the .exe file directory when compiling with a list of all the functions used and their 
hashes. It can be used to find unresolved externals and can be added to BlackOps3.txt when using cerberus to name every function.

- Debug Output: Outputs information about the inection process, useful if the injection isn't working correctly.

- Use Different GSC Header: This will change the GSC file being overwritten to a custom one. This can be used to have multiple custom GSC files
loaded ingame. This also means that any functions in the original GSC will be overwritten, and if one of them is referenced by another
GSC file an unresolved external error will be thrown. To prevent this, check the GSC file in cerberus and move all the functions to your
custom GSC file. Checksums also need to match the overwritten GSC file to let others join the server, so use #checksum (more info below).


Notes:
- If your math or boolean operators aren't working how they should, try wrapping them in ().
- Compiled files can be opened in cerberus, but larger files might not open due to cerberus's limitations. 
- This is not a perfect compiler, and bugs are to be expected. If you find a bug, first test it and make sure it isn't an error on your end. If
you are sure that it is a compiler error, report it.


Extra Syntax:
#namespace, #path and #checksum do not need to be used when compiling and injecting the normal way. If you are using a different GSC header #checksum
is required for others to join your server, and #namespace if you are referencing the script from another script. #path is not very useful at all, but
i have added it incase someone needs it for their own injector.

#namespace:
- Defines the namespace that the GSC file will be used. 
Default is "duplicate_render"
usage:
#namespace duplicate_render;

#path:
- Defines the path that the GSC file says it has. The path has to be more than 1 character.
Default is "scripts/shared/duplicaterender_mgr.gsc"
usage:
#path scripts/shared/duplicaterender_mgr.gsc;

#checksum:
- Defines the checksum of the GSC file. 
Default is 2337484f
usage:
#checksum "2337484f"; //need the quotation marks


Utilities Folder:
This contains a simple program that hashes strings, useful for figuring out hashed names or variables. 
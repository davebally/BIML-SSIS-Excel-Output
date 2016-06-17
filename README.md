BIML Task to generate SSIS pacakges to output Excel Spreadsheets

"Everything ends up in Excel"  

Frustratingly write Excel sheets is a pain, for any number of well documented reasons.  This project is a simple BIML process around EPPlus ( http://epplus.codeplex.com/ ) to semi auto generate SSIS package that A) are reliable B) perform well.

You will need to push EPPlus to the GAC, and also set the variable EPPlus to point to the DLL ( not sure why it cant be found in the GAC ?! ).
SQLConn needs be changed to point to your database.
You will also need to create a ProjectParameter “OutputExcelFile” , again not sure why this is not being autocreated ?!.

Usage is pretty simple create one or more ExportFile Objects passing in a FileName ( which will be overridden at run time by the project parameter ) and a Package Name.
Add to the WorkSheetList List of the Export Files WorkSheet Objects which are created with the Parameters(SheetName,SQLStatement,SQLConn) and you should be good to go.



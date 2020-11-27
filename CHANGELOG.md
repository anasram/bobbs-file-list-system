## 3.2.0 (2005-04-18)

* New
	* Added a HTML style to the program so links stand out more. (Bug: 1176560) (Brandon)
	* Revamped HTML of revamped documentation. (Monica)
* Updated
	* Fixed new/updated notification. Wasn't working correctly for files. (Bug: 1176524) (Brandon)
	* Fixed oversize text not having '...' at the end. (Bug: 1176469) (Brandon)
	* Changed quite a few variables from being rounded with `floor()` to `round()` which is more accurate for its purposes. (Bug: 1178757) (Brandon)
	* Optimized the `allowed()` function. Switched it to argument-based instead of accessing global variables. Saved about 8 lines of code. (Bug: 1178755) (Brandon)
	* Optimized the `flscandir()` function. Instead of doing it's own file testing it now uses `allowed()` to test them. Saved a few lines of code. (Bug: 1178753) (Brandon)
	* Revamped documentation. (Monica/Brandon)
	* Fixed bug with all stats. (Bug: 1185356) (Brandon)

## 3.1.8 (2005-04-01)

* New
	* This version is a stripped down version of File Manage. Came with the usable features, fixes, and optimizations that been ocurring to File Manage. (Brandon)
	* Added properties dialogue. Give more specific and additional information. (Bug: 1175035) (Brandon)
	* Added auto icons detection. (Bug: 1175036) (Brandon)
	* Added notes to things that may need some explainations. (Bug: 1175037) (Brandon)
	* Added hit counter and pageview counter. (Bug: 1177250) (Brandon)
* Updated
	* Many bug fixes and many optimization and stabalizations. (Bug: 1175042) (Brandon)
	* Fixed some displaying of files that should not be viewed. (Bug: 1175038) (Brandon)
	* Fixed an issue that if the title or body HTML tags were capitolized the program wouldn't recognize them. (Bug: 1175039) (Brandon)

## 3.1.6 (2005-02-17)

* New
	* Nothing.
* Updated
	* Minor optimization and bug fixes (Brandon)

## 3.1.5c (2005-02-16)

* New
	* Nothing.
* Updated
	* Added comments to the whole program. (Bug: 1124225) (Brandon)

## 3.1.5b (2005-02-10)

* New
	* Nothing.
* Updated
	* Found a simple bug with big concequences. (Bug: 1120498) (Brandon)

## 3.1.5 (2005-02-08)

* New
	* Now additional info supports HTML files. It shows the title if there is one, if not it will show body content, if there is none, then it will show the file as if it were text. (Bug: 1118843) (Brandon)
* Updated
	* Minor optimiztion. (Bug: 1118931) (Brandon)
	* Removed underline tags from column headers. Make it so sortable links stand out more. (Bug: 1118936) (Brandon)

## 3.1.2 (2005-01-14)

* New
	* Nothing.
* Updated
	* Fixed some major sorting issues. (Bug: 1118828) (Brandon)

## 3.1.0 (2004-11-26)

* New
	* In `non-lang`: Added ability to sort by file name, size, or type in ascending or descending order. Just click onthe corisponding column titles at the top. (Bug: 1038647) (Brandon)
* Updated
	* Nothing.

## 3.0.8 (2004-11-05)

* New
	* In `non-lang`: The ability to scan all sub directories with the 'all stats' feature has been added. This replaced a less optimized, limited, and very lengthy set of code. (Bug: 1061179) (Brandon)
* Updated
	* In `non-lang`: Fixed a bug where Windows' PHP would halt while 'all stats' was scanning files. It only occured on CGI-Windows PHP and only after a few thousand files/dirs were scanned. (Bug: 1054824) (Brandon)

## 3.0.6 (2004-10-27)

* New
	* In `non-lang`: Added "view sub directoriy files" option. This is in testing, and will eventually have the ability to view two layers of sub directories (currently only 1). (part of bug: 1042676) (Brandon)
* Updated
	* In `non-lang`: Added more text file types (log, nfo, diz). (Brandon)
	* In both: Some bug testing and minor tuning. (Brandon)

## 3.0.5 (2004-10-23)

* New
	* In both: Removed "music info" stuff and moved that info to the "Additional Information" column. This now contains infor for text, images, autio, and video files. The autio and video files have bitrate and length and the video files have resolution also. Now all we need it `.zip` file info. (part of bug: 1051833) (Brandon)
* Updated
	* In both: Added a pre-made list/example of acceptable file types and icons that go with it (based on Apache icons) so it is easier to use, and looks better. (bug: 1052953) (Brandon)
	* Updated Documentation for updates since `3.0.0` (Brandon)

## 3.0.3 (2004-10-22)

* New
	* In both: Added additional information column. Currently only has text and image additional info, but more will come. (part of bug: 1051833) (Brandon)
* Updated

## 3.0.1 (2004-10-20)

* New
	* In both: Made the array generated of all files to write to a file to keep track of how many files there as a database. It logs, but isn't accessed yet. (part of bug: 1048094) (Brandon)
* Updated
	* Nothing.

## 3.0.0 (2004-10-16)

* New
	* In both: Made all stats update time change based on the number of file and directories in the all stats file. The more files/dirs you have the longer it waits to update. (bug: 1048478) (Brandon)
* Updated
	* In both: Made code more optimized by moving some if and loop statements around. The program now goes through less info each execution. (bug: 1042681) (Brandon)
	* In both: Made the all stats scan scan 8 subdir levels deep (previously only 6). (bug: 1048480) (Brandon)

## 2.9.3 (2004-10-14)

* New
	* Nothing.
* Updated
	* In both: Fixed bug where non-standard file paths would make system fail. So we switched from `$loc1 = $DOC_ROOT . $cur_dir` to `$loc1 = dirname(__FILE__)` to allow for this. (bug: 1044973) (Bradley/Brandon)
	* In both: Rewrote code (because of above fix) to make less errors occur and be more optimized. (Brandon)

## 2.9.2 (2004-10-13)

* New
	* In both: Made the path at top links, so you can click on any one to go to a higher directory. Makes for easier navigating. (bug: 1044135) (Brandon)
* Updated
	* In both: Fixed bug where all stats were incorrect when accept file ending returned true twice. (bug: 1038650) (Brandon)

## 2.9.1 (2004-10-10)

* New
	* In `-lang`: Made the `organize_ord` feature work with a list of ignore words, isntead of just a couple of preset ones. This was nescisary for the internationalization. (bug: 1043596) (Brandon)
* Updated
	* In both: Minor optimization

## 2.9.0b (2004-10-08)

* New
	* Nothing.
* Updated
	* In `-lang`: Added some more set words to be translated due to language changes that I was anaware of.

## 2.9.0 (2004-10-08)

* New
	* Made a easily translatable version so that a language only needs to be translated on certain lines of a file (`filelist-lang-[lang abbriviation].list`) and can be used as set text. This build will be known as `-lang`. (Brandon)
* Updated
	* Fixed the bug where the program would add a `.` after the directory name not allowing this program to be used anywhere but in the root directory of the server. There were many core updates with this. (bug: 1042734) (Brandon)

## 2.8.8 (2004-10-07)

* New
	* Made code more optimized by making it only go through one full list of files instead of two. (bug: 1041602) (Brandon)
	* New docs (part of bug: 1042047) (Bradley)
	* Better copyright disclaimer/file headers (bug: 1042080) (Bradley)
* Updated
	* Made $ftype store as lowercase since there are things dependant on it. (bug: 1042061) (Brandon)

## 2.8.6 (2004-10-06)

* New
	* Added file: COPYRIGHT which contains all the contributers to the Bobb's File List System (BFLS) since they hold the copyright. (bug: 1042078) (Brandon)
	* Added a notification of copyright and a link for more info at bottom of pages displayed. (part of bug: 1042080) (Brandon)
* Updated
	* Nothing.

## 2.8.5 (2004-10-05)

* New
	* Nothing.
* Updated
	* Fixed an issue with the all stats where it started from base directory instead of file location (due to old programming). (bug: 1040954) (Brandon)
	* Fixed a problem with the organize ordanary filename starts where it didn't work. (bug: 1040953) (Brandon)

## 2.8.3 (2004-10-04)

* New
	* The ability to turn on/off the "total stats" info at bottom of page. (bug: 1038864) (Brandon)
* Updated
	* Changed from 1/0 switching to true/false for more obvious and easier use. (Brandon)
	* A lot of core rearanging to allow for better file handling and some bug fixes. (Brandon)
	* Made it so all subdirs and files can be accessed from one file instead of having a file in each subdirectory refering back to the main one. (bug: 1040300) (Brandon)

## 2.6.2 (2004-10-01)

* New
	* Nothing.
* Updated
	* Many updates to get ready for release on Source Forge. (Brandon)
	* Not much formal note keeping was taken until Source Forge. (Brandon :-/ )

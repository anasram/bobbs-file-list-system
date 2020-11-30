
# Bobb’s File List

[Demo](https://richstyle.org/downloads)

## System Requirements

### Webserver

* Webserver/PHP must have full permissions in its containing folder for this program to operate correctly.
* An Apache-based host webserver is recommended ([www.apache.org](http://www.apache.org/)).

### PHP

* PHP 7.0.0 or higher.
* ~PHP 4.2.0 or higher (certain features will be less optimized with PHP versions less than 4.3.0). The newest available version of PHP is recommended~.
* ~Note: If using Windows, PHP 4.3.6 or higher is strongly recommended ([www.php.net](https://www.php.net/)). Minimal testing has occurred with PHP5, so unless you want to test it for us, we recommend PHP4~.

### Memory

* At least 100KB of free memory on the server.

### Browser

* Internet Explorer 6 or higher (www.microsoft.com) or other equivalent browsers is recommended.
* Viewing of generated HTML pages must be done on a JavaScript enabled browser. Mozilla Firefox 1.0 or higher is recommended ([www.mozilla.org](https://www.mozilla.org/)).

### Other

* It is recommended that viewing of these text-based files (`README`s and PHP files) should be done in a highlighting editor such as PSPad ([www.pspad.com](http://www.pspad.com/)).

## Installing Bobb’s File List

Simply place filelist.php into a web server directory which has PHP 4.2.0 or higher installed. This can be renamed to anything you want, as long as it has a PHP-based extension or an extension recognized as PHP by the web server.

Hint: Rename the file `index.php` to make it the default index for the directory.

## Accessing Bobb’s File List

To access Bobb’s File List, open a web browser and type in the address of the file (e.g. `http://localhost/this/dir/filelist.php`).

You should see a nice list of all the files and sub-directories that are in the directory you installed the file to.

That’s it!

NOTE: If using `getid3()` for music or video files on large file systems (4000 or more files and directories), it is highly recommended to only use Unix-based operating systems such as Linux. Threaded operating systems such as Windows have known PHP issues that may cause problems in this software. Threaded operating systems may also have difficulty displaying hundreds of files in a single directory when using `getid3()`.

## Advanced Setup/Configuration

This is not required for the basic functioning of the program. Advanced configuration allows for further customization of the installation.

### Enabling `getid3()`

* Download the latest stable version from [sourceforge.net/projects/getid3/](https://sourceforge.net/projects/getid3/).
* Extract it to the location of the File List file in a subdirectory called `getid3`. Make sure that `getid3/getid3/getid3.php` is a valid path from the File List file.

_getid3_ will slow down File List’s process (more so on Windows than other operating systems) and there will most likely be some setup required to enable `getid3()`. Follow the instructions given and/or read `getid3()`’s readme file.

### Setting Up Acceptable File Types

Open the `.php` file in a text editor, such as Notepad on Windows systems. Look for the following lines:

```php
$accept = array(
''
);
```

This lists acceptable file endings. For best results, include the `.` in a desired file extension. This is great if you just want to show `.mp3`’s or just `.jpg`’s. If you want more than one file type shown, separate them with commas like this: `'.jpg','.gif','.png'`. If you add `''` as the last item in the list, it will display all file types.

If you have `$auto_icon` set to `true`, you do not need to concern yourself with this section between the `<<` and `>>`. With this feature enabled, icons are automatically set when file types are specified in the `$accept` array.

```php
<<

$iconlink = array(
'/icons/unknown.gif'
);
```

This is the path to the icon that will be displayed next to the filename. The array key will correspond to the keys in the \$accept array. This allows different icons to be used for .gif files and .jpg files to help distinguish between file types. If used, it is best to use the `/icons/unknown.gif` path for a `''` accepted type. Many common file extensions have been added to the Auto Icon feature. If Auto Icon is enabled, you can ignore this array.

For example: If these were the set arrays:

```php
$iconlink = array(
'/icons/music.gif',
'/icons/music2.gif',
'/icons/unknown.gif'
);
$accept = array(
'.mp3',
'.wma',
''
);
```

This would display all files in the directories with an `unknown` icon next to them. But it would display `.mp3` files and `.wma` files with music-looking icons -- both unique to be able to distinguish between them.

### Additional Setup Options

Open the `.php` file in a text editor, such as Notepad on Windows systems, and look for the lines in the following table:

Variable | Syntax/value | example/default
---|---|---
`display_new` | `true` | Display `new` when the file or directory is new (according to the OS’s value). |
`display_updated` | `true` | Display `updated` when the file or directory has been updated (according to the OS). |
`new_time_secs` | `60 * 60 * 24 * 14` | Displays `new` and `updated` deadline. Use simple math to convert 14 days to seconds. |
`error_spacer`<br/>`error_spacer2` | `0.5` (per word errors)<br/>`0.3` (per segment errors) | These variables deal with the searches. A value of `0` requires an exact match, while a value of `1` will accept all words, so somewhere in between would be a good value. An `error_spacer2` value less than the `error_spacer` value would be ideal.
`show_all_stats` | `false` | Show or don’t show the `totals` stats at the bottom of the page. This includes the number of directories and files. It also displays the total file size used by the files in the File Manage system.
`organize_ord` | `true` | When organizing the files and directories, ignore leading articles: 'the', 'an', and 'a'.
`show_add_info` | `true` | This will display the additional file information some files, such as images, text, HTML, PHP, music, and video files, may have.<br/>Music and video files require `getid3()`: [sourceforge.net/projects/getid3/](https://sourceforge.net/projects/getid3//projects/getid3/). Allow `getid3/getid3/getid3.php` to be a valid path from the file manage file. |
`line_break` | `"\n"` | This is the type of line break files created by this program. The program does not care what type you use as long as it is one of the following:<br/>`"\n"` -- General default; works on all systems, but may not format correctly on some text editors that were not designed for Unix-text viewing<br/>`"\r"` -- MacOS 9 and older default<br/>`"\n\r"` -- Windows/DOS default; this is the only line break that Notepad displays correctly
`auto_icon` | `true` | This feature allows an administrator to edit the acceptable file extensions without having to change the linked icon images. Keep as `true` unless custom icons or obscure extensions (that icons should be linked to) are being used.

## Troubleshooting

Symptom | Problem | Solution
---|---|---
The pages don't load completely (using either Windows or Unix-based OS). Some files are shown but not all, and it is not showing the legal stuff at the bottom of every page. | Most likely, you have `getid3()` installed in the folder. | Rename or remove the getid3 folder and see if the pages load fully then. If they still do not (or you never had `getid3()` in the first place), then there may be too many files in the directory for Windows' PHP to handle. There are known PHP issues with threaded operating systems that have yet to be resolved. Remove some files. If that does not fix it, there may be a File List or PHP install problem. Download/install(compile) the newest version of both and see if that fixes anything. If not, report a bug to File List immediately. | 
I am running a Unix-based OS and every time I access the File List file I receive a "Cannot open/write to file (`filelist/_a filename here_`). Likely to be a permissions problem." Or even worse, a 403 Forbidden message pops up. | If the error says "Cannot open", then Apache (or your http server) does not have read access in the directory where File List is installed. If it says "Cannot write to", then Apache (or your http server) does not have write access in the directory where File List is installed in. | Depending on the owner of the folder, chmod 775 or 777 (775 if the current owner is Apache or your https server and 777 if the owner is something else -- possibly your login). | 
I am running Windows and every time I access the File List file I receive a "Cannot write to file (`filelist/_a filename here_`). Likely to be a permissions problem." | Most likely, the File List file or the containing folder is set to "Read-only" in its properties. | Right-click on the containing folder, uncheck (or check, then uncheck) the "Read-only" attribute near the bottom, and click OK. Select "Apply changes to this folder, subfolders and files" and click OK. If this did not fix your problem, you may have more serious permission problems. | 
I am experiencing long load times, even on local connections to the server. | Especially if `getid3()` is installed, the additional info column can take up a lot of processing time and resources as it gathers all the available info. This is a lot more significant as more files are added into a single directory. | Remove some files in the directory or disable the additional info column in the settings of the file (approx. line 47). If the problem still occurs with less than 20-30 files in the directory, there may be a more serious issue. Download the latest version of PHP and File List. If it still continues, report a bug to File List immediately.

Thanks for downloading Bobb’s File List!

modified: <time>2005-04-08</time>

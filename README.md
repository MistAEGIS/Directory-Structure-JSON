# Directory Structure JSON

This module exposes functions with which you can:

* Get a JSON structure of a folder (including subdirectories and files)
* Traverse a structure, giving callbacks to execute when a file or folder is found

## Get directory structure

``` javascript
var DirectoryStructureJSON = require('directory-structure-json');
var basepath = 'path/to/some/folder';

DirectoryStructureJSON.getStructure(basepath, function (err, structure, total) {
    if (err) console.log(err);

    console.log('there are a total of: ', total.folders, ' folders and ', total.files, ' files');
});
```

## Traverse structure
The structure retrieved from the function above can be traversed.


``` javascript
var DirectoryStructureJSON = require('directory-structure-json');
var basepath = 'path/to/some/folder';

DirectoryStructureJSON.traverseStructure(structure, basepath,
function (folder, path) {
    console.log('folder found: ', folder.name, 'at path: ', path);
},
function (file, path) {
    console.log('file found: ', file.name, 'at path: ', path);
});
```

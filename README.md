# PHP Build Subfolders
**Build Subfolders** is a PHP function which parses a filepath-string and creates new subfolders, sequentially.

_____

## `Build_Subfolders($File_Path)` function

```

function Build_Subfolders($File_Path) {

  $File_Path_Completed = '';

  $File_Path_Array = explode('/', $File_Path);

  while (count($File_Path_Array) > 0) {

    if (!is_dir($File_Path_Completed.'/'.$File_Path_Array[0])) {

      mkdir($File_Path_Completed.'/'.$File_Path_Array[0]);
    }

    $File_Path_Completed .= '/'.$File_Path_Array[0];

    array_shift($File_Path_Array);
  }
}

```

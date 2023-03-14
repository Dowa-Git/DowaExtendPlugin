## [Libraries](../../Libraries.md) > [File](../FileLibrary.md)
# **OpenFolderDialog**  
* ``Open Folder dialog`` with unreal engine ui. 
* Syntax  
    ```
    static void OpenFolderDialog
    (
        const FString& DialogTitle, 
        const FString& DefaultPath, 
        FString& OutFileNames
    )
    ```  
* Parmeters  
    | Parameter | Description |
    | -- | -- |
    | DialogTitle | Title string for dialog ui |
    | DefaultPath | First path show when the ui opened |
    | OutFileNames | Output string of the selected folder. |

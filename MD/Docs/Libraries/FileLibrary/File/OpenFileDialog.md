## [Libraries](../../Libraries.md) > [File](../FileLibrary.md)
# **OpenFileDialog**  
* ``Open file dialog`` with unreal engine ui. 
* Syntax  
    ```
    static void OpenFileDialog
    (
        const FString& DialogTitle, 
        const FString& DefaultPath,
        const FString& FileTypes, 
        TArray<FString>& OutFileNames
    )
    ```  
* Parmeters  
    | Parameter | Description |
    | -- | -- |
    | DialogTitle | Title string for dialog ui |
    | DefaultPath | First path show when the ui opened |
    | FileTypes | The extension for file type specific |
    | OutFileNames | Output array of the selected files. |

## [Libraries](../../Libraries.md) > [Asset](../AssetLibrary.md)
# **ImportAsset**  
* ``Import the asset`` with specified import type and fbx file.  
* Syntax  
    ```
    static bool ImportAsset
    (
        EFBXImportType ImportType,  
        const FString& RawPath,  
        const FString& DestPath,  
        const FString& DestName,  
        const FString& TexturePath,  
        const FString& MasterMaterialPath  
    )
    ```  
* Parmeters  
    | Parameter | Description |
    | -- | -- |
    | ImportType | |
    | RawPath | path of fbx file |
    | DestPath | import destination directory |
    | DestName | import name.[^1] |
    | TexturePath | path of texture images directory |
    | MasterMaterialPath| path of master material path |
* Return  
returns the success status for import process.

[^1]: if this parameter not given, tool make the name automatically.
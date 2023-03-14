## [Libraries](../../Libraries.md) > [Asset](../AssetLibrary.md)
# **ImportAssetAuto**  
* ``Import the asset`` with specified import type and fbx file.  
* Basically, same process with [`ImportAsset`](../../DowaAssetLibrary.md#importassetauto), but the tool guess the FBXImportType with specified fbx file path.   
* Syntax  
    ```
    static bool ImportAssetAuto
    (
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
    | RawPath | path of fbx file |
    | DestPath | import destination directory |
    | DestName | import name.[^1] |
    | TexturePath | path of texture images directory |
    | MasterMaterialPath| path of master material path |
* Return  
returns the success status for import process.
[^1]: if this parameter not given, tool make the name automatically.
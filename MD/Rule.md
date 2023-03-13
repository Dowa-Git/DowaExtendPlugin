[material_type_tag]: #tag-for-material-type "Tag of material type documents"
[asset_option]: #asset-option "Asset option documents"
[detail_option]: #detail-option "detail option documents"

# File formatting rule
## General format
***
* Shader Name
  * Shader name defined from the shader node of the maya hypergraph.
  * Shader name also being the material element name of unreal editor.
  * basic shader name foramt like under below.  
    {[MaterialTypeTag][material_type_tag]}\_{[AssetOption][asset_option]}\_{[DetailOption][detail_option]}

* FBX Path  
  {ProjectPath[^1]}/Content/Asset/{AssetType[^2]}/{AssetName}/{FBXType[^3]}_{AssetName}_N.fbx

* Texture Path:  
  {ProjectPath}/sourceimages/{[MaterialTypeTag][material_type_tag]}\_{AssetName}\_{DetailName}\_{TextureType[^4]}.{TextureImageExtension[^5]}
  
### Tag for material type
***
* Indicates the type of material as an abbreviation.
* Basic Format of abbreviation like under below. all section would be one letter.  
    `{TargetAssetType}{BlendMode}{ShadingModel}`
* Character material tag list
  | Tag | Description | Blend Mode | Shading Model | Inheritance |
  |-- | -- | -- | -- | :--: |
  | `COD` | General material | Opaque | Default Lit | Master |
  | `COS` | General skin material | Opaque | Subsurface Profile | Master |
  | `CMD` | Masked material | Masked | Default Lit | Master |
  | `CMS` | Masked skin material | Masked | Subsurface Profile | Master |
  | `CTD` | Translucent material | Translucent | Default Lit | Master |
  | `CGS` | Glass | Translucent | Default Lit | CTD |
  | `CEB` | Eyeball | Opaque | Subsurface Profile | COS |
  | `CLS` | Eyelens | Translucent | Default Lit | CTD |
  | `CLH` | Eyelash | Masked | Default Lit | CMD |
  | `CTE` | Teeth | Opaque | Subsurface Profile | COS |
  | `CTO` | Tongue | Opaque | Subsurface Profile | COS |
* Background material tag list
  | Tag | Description | Blend Mode | Shading Model | Inheritance |
  |-- | -- | -- | -- | :--: |
  | `BOD` | General material | Opaque | Default Lit | Master |
  | `BOS` | General skin material | Opaque | Subsurface Profile | Master |
  | `BMD` | Masked material | Masked | Default Lit | Master |
  | `BMS` | Masked skin material | Masked | Subsurface Profile | Master |
  | `BTD` | Translucent material | Translucent | Default Lit | Master |
  | `BGS` | Glass | Translucent | Default Lit | BTD |


### Asset Option
***
* Asset option is the section for make the basic path for seek the texture image file.
* If the asset using the category option from pipeline tool, the category name should be specified in the shader name with ``.mark``.
* Asset option format  
  | Case | Format | Reference path for texture seeking |
  | -- | -- | -- | 
  | General | {AssetName} | {ProjectPath[^1]}/sourceimages/{AssetName}/
  | Has Category | {Category}.{AssetName} | {ProjectPath}/sourceImages/{Category}/
### Detail Option
***
* Detail Option is the section for make final path for seek the texture image file.
* with detail option, the importer will be make the path like under below.

      {AssetOptionPath}/{MaterialTypeTag}_{AssetName}_{DetailName}_{TextureType}

* In some case, you may want the several materials using same texture.   
  for that, the number without duplicates should specified with ``.mark``. 
* Detail option format  
  | Case | Format |
  | -- | -- |
  | General | {DetailName} | 
  | Have to make another material with same texture | {DetailName}.{Number}

[^1]: Project path of maya.
[^2]: Define the assets type.  
    | Tag | Asset Type |
    | -- | -- |
    | `CHR` | Character |
    | `PRP` | Prop |
    | `BG` | Background | 

[^3]: Define the assets fbx type.  
    | Tag | FBX Type |
    | -- | -- |
    | `SM` | Mesh data for generate the static mesh |
    | `SK` | Mesh data for generate the skeletal mesh (include rig data) |
    | `A` | joint key data for generate the animation sequence | 

[^4]: Define type of texture
    | Tag | Texture Type |
    | -- | -- |
    | `BaseColor` | Base color texture(diffuse, albedo). |
    | `ORM` | ORM mask texture(opacity, roughnees, metalic). |
    | `Normal` | Normal texture. |
    | `Emissive` | Emissive mask texture. |
    | `OpacityMask` | Opacity mask texture. |
    | `SSSMask` | Subsurface skin mask texture. |

[^5]: image format extension (tga, png, jpg, etc..)



[material_type_tag]: #material-type-tag "Tag of material type documents"
[asset_option]: #asset-option "Asset option documents"
[detail_option]: #detail-option "detail option documents"
[asset_type]: #asset-type "type of asset"
[fbx_type]: #fbx-type "type of fbx"
[texture_type]: #texture-type "type of texture"

[^1]: Project path of maya.

[^2]: The part of assets name (e.g : arm, leg, head, etc...) 

[^3]: image format extension (e.g : tga, png, jpg, etc..)


# File formatting rule
## General format
***
* Shader Name  
  * Shader name defined from the shader node of the maya hypergraph.
  * Shader name also being the material element name of unreal editor.
  * basic shader name foramt like under below.  
    {[MaterialTypeTag][material_type_tag]}\_{[AssetOption][asset_option]}\_{[DetailOption][detail_option]}

* FBX Path  
  > {ProjectPath[^1]}/Content/Asset/{[AssetType][asset_type]}/{AssetName}/{[FBXType][fbx_type]}_{AssetName}_N.fbx

* Texture Path:  
  > {ProjectPath}/sourceimages/{[MaterialTypeTag][material_type_tag]}\_{AssetName}\_{DetailName[^2]}\_{[TextureType][texture_type]}.{TextureImageExtension[^3]}
  
## Sections
***
* ### **Material type tag**
  * Indicates the type of material as an abbreviation.
  * Basic Format of abbreviation like under below. all section would be one letter.  
      > {TargetAssetType}{BlendMode}{ShadingModel}
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

* ### **Asset Option**
  * Asset option is the section for make the basic path for seek the texture image file.
  * If the asset using the category option from pipeline tool, the category name should be specified in the shader name with ``.``mark.
  * Asset option format  
    | Case | Format | Reference path for texture seeking |
    | -- | -- | -- | 
    | General | {AssetName} | {ProjectPath[^1]}/sourceimages/{AssetName}/
    | Has Category | {Category}.{AssetName} | {ProjectPath}/sourceImages/{Category}/

* ### **Detail Option**
  * Detail Option is the section for make final path for seek the texture image file.
  * with detail option, the importer will be make the path like under below.
    > {AssetOptionPath}/{MaterialTypeTag}\_{AssetName}\_{DetailName}\_{TextureType}
  * In some case, you may want the several materials using same texture.   
    for that, the number without duplicates should specified with ``.``mark. 
  * Detail option format  
    | Case | Format |
    | -- | -- |
    | General | {DetailName} | 
    | Have to make another material with same texture | {DetailName}.{Number}

* ### **Asset Type**
  * Define the asset type.  
    | Tag | Asset Type |
    | -- | -- |
    | `CHR` | Character |
    | `PRP` | Prop |
    | `BG` | Background | 

* ### **FBX Type**
  * Define the assets fbx type.  
    | Tag | FBX Type |
    | -- | -- |
    | `SM` | Mesh data for generate the static mesh |
    | `SK` | Mesh data for generate the skeletal mesh (include rig data) |
    | `A` | joint key data for generate the animation sequence | 

* ### **Texture Type**
  * Define type of texture
    | Tag | Texture Type |
    | -- | -- |
    | `BaseColor` | Base color texture(diffuse, albedo). |
    | `ORM` | ORM mask texture(opacity, roughnees, metalic). |
    | `Normal` | Normal texture. |
    | `Emissive` | Emissive mask texture. |
    | `OpacityMask` | Opacity mask texture. |
    | `SSSMask` | Subsurface skin mask texture. |


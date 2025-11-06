# EternalReturnResource
if 

## You may need to know  
The image mapping relationship is located in most files in the data directory. The key represents the unique ID of the item    

### character Images  
The character image is composed of character id-skin id, including optional items such as Result and Profile. Please check them yourself for details


### Resources Type Code
```kotlin
enum class ImageResourcesType(val path: String, val fileType: String) {
    Weapon("/weapon/", ".png"),
    TierFull("/tier/full/", ".png"),
    TierRound("/tier/round/", ".png"),
    Character("/character/", ".png"),
    Item("/item/", ".png"),
    TacticalSkill("/tactical/skill/", ".png"),
    TraitSkill("/trait/skill/", ".png"),
    TraitSkillGroupPlaceholder("/trait/group/wilson", ".png"),
    TraitSkillGroup("/trait/group/", ".png");


    val traitSkillIdRegex = "[0-9]+".toRegex()
    fun getGeneralPath(name: String): String {
        return "/resources/images${this.path}$name${this.fileType}"
    }

    companion object {
        fun getCharacterPath(
            characterId: Int,
            skinId: Long,
            imageType: DakGGCharacterImgType,
        ): String {
            return "/resources/images${Character.path}${characterId}/${imageType.value}/${skinId}${Character.fileType}"
        }
    }
}
```

## You must know
© All Rights Reserved.  Eternal Return and all related logos are trademarks of Nimble Neuron, inc. or its affiliates.

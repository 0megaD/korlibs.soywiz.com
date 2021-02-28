---
layout: default
title: "Skeleton"
title_prefix: KorGE
fa-icon: fa-child
priority: 200
---

Skeletal-based animations give allows you to reduce the assets size, while allowing to create unique and smooth animations.

# KorGE v2.0+

## Spine

You can use Spine by adding the following dependency in your 'korge' block.

```kotlin
korge {
	supportSpine()
}
```

### Simple example

Here's the bare minimum required to load & display an exported Spine character with at least one animation.

If you are using a .skel binary file, use `readSkeletonBinary` instead of `readSkeletonJson`

```kotlin
override suspend fun Container.sceneInit() {
    val atlas = resourcesVfs["example.atlas"].readAtlas()
    val skeleton = resourcesVfs["example.json"].readSkeletonJson(atlas, 1f)
  
    val skel = Skeleton(skeleton)
    val stateData = AnimationStateData(skeleton)
    val state = AnimationState(stateData)
    
    state.setAnimation(0, "idle", true)
    state.apply(skel)
    
    skel.updateWorldTransform()
    
    val view = SkeletonView(skel, state)
    addChild(view)
}
```

## DragonBone

TK

### Simple Example

TK

# KorGE (pre v2.0)

## DragonBones

You can use DragonBones by adding the dependency:

```kotlin
dependencies {
    commonMainApi "com.soywiz:korge-dragonbones:$korgeVersion"
}
```

### Using in code

```kotlin
val factory = KorgeDbFactory()
factory.parseDragonBonesData(Json.parse(resourcesVfs["Dragon/Dragon_ske.json"].readString())!!)
factory.parseTextureAtlasData(
    Json.parse(resourcesVfs["Dragon/Dragon_tex.json"].readString())!!,
    resourcesVfs["Dragon/Dragon_tex.png"].readBitmapOptimized().toBMP32()
)
val armatureDisplay = factory.buildArmatureDisplay(armatureName = "Dragon", dragonBonesName = "Dragon")!!.position(100, 100)
```

The ArmatureDisplay is a view that can be attached to any container.
Also it contains the `armature` and the `animation` so you can apply animations to it.

```kotlin
class KorgeDbArmatureDisplay : Container(), IArmatureProxy {
    // ...
    val armature: Armature
    val animation: Animation

}
```

# Unreal Engine

Misc

[Actor Lifecycle](https://docs.unrealengine.com/5.3/en-US/unreal-engine-actor-lifecycle/)

[EPIC - Smart Pointers](https://docs.unrealengine.com/5.3/en-US/smart-pointers-in-unreal-engine/)
[Wiki - Smart Pointers](https://unrealcommunity.wiki/pointer-types-m33pysxg)

[Optimizing Shader](https://calvinatorrtech.art.blog/2023/12/20/optimizing-shaders-in-unreal-engine/)

[Delegates](https://benui.ca/unreal/delegates-advanced/)

[DataAssets vs DataTables](https://benui.ca/unreal/data-driven-design/)

[UPROPERTY](https://benui.ca/unreal/uproperty/)

Profilling/Metrics

[Stat Commands](https://www.tomlooman.com/unreal-engine-profiling-stat-commands/)

[Optimization](https://www.tomlooman.com/unrealengine-optimization-talk/)

[PSO Caching](https://www.tomlooman.com/psocaching-unreal-engine/)

Tips   

CTRL+SHIFT+, -> opens GPU visualizer
CTRL+SHIFT+H -> shows FPS/MS

Debug an UnrealEngine cooked shipped build with code changes?
Use `-basedir=E:\ProjectName\Binaries\Win64` to make your Visual Studio game instance act like it was being run with your cooked shipping assets.

Console Commands
`obj list` - shows all UObjects grouped by class
`obj list class={CLASSNAME}` - shows all UObjects of the {CLASSNAME}
`obj dump /Path/To/Obj` - shows all UPROPERTIES of an object
`obj refs name=/Path/To/Obj shortest` - lists what's keeping the obj from getting GC'd
`obj gc` - triggers a garbage collection

Logging

`log LogStreaming verbose` - See when assets get loaded
`log LogGarbage verbose` - see detailed GC timings
`bUseLoggingInShipping=true` - enables loggin in shipping builds
 
 Set Instigators and Names at "Project Settings -> Engine -> Cooker -> Cooker Progress Display Mode"
 to see which cooking asset additional info.

UI
[UMG-Slate-Compendium](https://github.com/YawLighthouse/UMG-Slate-Compendium)   

UE Networking
[Multiplayer Network Compendium](https://cedric-neukirchen.net/docs/category/multiplayer-network-compendium)

## C++

[C++ Interfaces](https://www.stevestreeting.com/2020/11/02/ue4-c-interfaces-hints-n-tips/)

UENUM

Get the string from an UENUM -> `*UEnum::GetValueAsString(payload->Source)`

[Iterate over UEnum](https://benui.ca/unreal/iterate-over-enum-tenumrange/)

```
UENUM()
enum class EAnimal : uint8
{
	Cat,
	Dog,
	Elephant,
	Count UMETA(Hidden)
};
ENUM_RANGE_BY_COUNT(EAnimal, EAnimal::Count);

for (EAnimal Animal : TEnumRange<EAnimal>())
{

}
```

# Mixamo

## No IK Retargetting needed

https://www.youtube.com/watch?v=HZyxPVfeQt8

-This video shows how to use Mixamo animations without needing to retaget it back to UE character skeleton.
-The `.fbx` file for the UE skeleton mesh can be obtained from the Mixamo Converter tool (Mixamo Converter from Terriblis Studio).
-Then the character should be uploaded to Mixamo to select the animation.
-After downloading the animation using the UE character, we need to pass it through the converter tool.
-After conversion, import into a UE project.



## IK Retargetting

https://www.youtube.com/watch?v=BTnSMAbu5cI

-Download T-pose character from Mixamo;
-Export FBX from both Mixamo and UE SK and import them on Blender to match pose;
-Import modified mixamo char into UE; (Use T0 as ref pose option)
-Create IK rig for the Mixamo char; Create bone chains to match the UE one;
-Create IK Retargeter for the mixamo to UE one;


## IK Retargetting explained in details (Settings, Goals and Solvers)

https://www.youtube.com/watch?v=eYal6taYUfE


# Unreal Engine

Misc

[Actor Lifecycle](https://docs.unrealengine.com/5.3/en-US/unreal-engine-actor-lifecycle/)

[Smart Pointers](https://docs.unrealengine.com/5.3/en-US/smart-pointers-in-unreal-engine/)

[Optimizing Shader](https://calvinatorrtech.art.blog/2023/12/20/optimizing-shaders-in-unreal-engine/)

[Delegates](https://benui.ca/unreal/delegates-advanced/)

[DataAssets vs DataTables](https://benui.ca/unreal/data-driven-design/)

[UPROPERTY](https://benui.ca/unreal/uproperty/)

Profilling/Metrics

[Stat Commands](https://www.tomlooman.com/unreal-engine-profiling-stat-commands/)

[Optimization](https://www.tomlooman.com/unrealengine-optimization-talk/)

[PSO Caching](https://www.tomlooman.com/psocaching-unreal-engine/)

Tips


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




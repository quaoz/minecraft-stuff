I'm running [GraalVM](https://www.graalvm.org/) on mac and using [MultiMC](https://multimc.org/) with 4096 MB minimum and maximum RAM allocated.

My JVM arguments are:

`-XX:+UnlockExperimentalVMOptions -XX:+UseG1GC -XX:+AlwaysPreTouch -XX:+ParallelRefProcEnabled -XX:G1NewSizePercent=30 -XX:G1MaxNewSizePercent=50 -XX:G1ReservePercent=20 -XX:G1HeapWastePercent=5 -XX:+DisableExplicitGC -XX:+UseNUMA -XX:MaxTenuringThreshold=15 -XX:MaxGCPauseMillis=90 -XX:G1HeapRegionSize=8M -XX:GCPauseIntervalMillis=150 -XX:-UseGCOverheadLimit -XX:SurvivorRatio=160 -XX:+PerfDisableSharedMem -XX:TargetSurvivorRatio=90 -XX:MaxTenuringThreshold=15 -Dfml.ignorePatchDiscrepancies=true -Dfml.ignoreInvalidMinecraftCertificates=true  -XX:+UseCompressedOops -XX:+OptimizeStringConcat -XX:ReservedCodeCacheSize=2048m -XX:+UseCodeCacheFlushing -XX:SoftRefLRUPolicyMSPerMB=5000 -XX:ParallelGCThreads=10 -XX:+EnableJVMCI -XX:+UseJVMCICompiler -XX:+EagerJVMCI -Djvmci.Compiler=graal -Dgraal.ShowConfiguration=info`

The last few arguments (`-XX:+EnableJVMCI -XX:+UseJVMCICompiler -XX:+EagerJVMCI -Djvmci.Compiler=graal`) aren't needed if your running Graal.

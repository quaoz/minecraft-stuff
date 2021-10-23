I'm running [GraalVM](https://www.graalvm.org/) on mac and using [GDLauncher](https://gdevs.io/) with 3072 MB maximum RAM allocated.

My JVM arguments are:

`-Xmx3G -Xms3G -Xmn512m -XX:+UnlockExperimentalVMOptions -XX:+UseG1GC -XX:+AlwaysPreTouch -XX:+ParallelRefProcEnabled -XX:+DisableExplicitGC -XX:+UseNUMA -XX:-UseGCOverheadLimit -XX:+PerfDisableSharedMem -XX:+UseCompressedOops -XX:+OptimizeStringConcat -XX:+EnableJVMCI -XX:+UseJVMCICompiler -XX:+EagerJVMCI -XX:-UsePerfData -XX:+UseCodeCacheFlushing -XX:ParallelGCThreads=4 -XX:ConcGCThreads=2 -XX:G1MixedGCCountTarget=8 -XX:MaxGCPauseMillis=100 -XX:GCPauseIntervalMillis=150 -XX:MaxTenuringThreshold=15 -XX:TargetSurvivorRatio=75 -XX:ReservedCodeCacheSize=1356m -Dgraal.CompilerConfiguration=enterprise -Dgraal.ShowConfiguration=info -XX:SurvivorRatio=8 -Dfml.ignorePatchDiscrepancies=true -Dfml.ignoreInvalidMinecraftCertificates=true`

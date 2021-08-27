I'm running [GraalVM](https://www.graalvm.org/) on mac and using [GDLauncher](https://gdevs.io/) with 4096 MB maximum RAM allocated.

My JVM arguments are:

`-XX:+UnlockExperimentalVMOptions -XX:+UseG1GC -XX:+AlwaysPreTouch -XX:+ParallelRefProcEnabled -XX:+DisableExplicitGC -XX:+UseNUMA  -XX:-UseGCOverheadLimit -XX:+PerfDisableSharedMem  -Dfml.ignorePatchDiscrepancies=true -Dfml.ignoreInvalidMinecraftCertificates=true  -XX:+UseCompressedOops -XX:+OptimizeStringConcat  -XX:+EnableJVMCI -XX:+UseJVMCICompiler -XX:+EagerJVMCI -Djvmci.Compiler=graal -Dgraal.ShowConfiguration=info`

The last few arguments (`-XX:+EnableJVMCI -XX:+UseJVMCICompiler -XX:+EagerJVMCI -Djvmci.Compiler=graal`) aren't needed if your running Graal.

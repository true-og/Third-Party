# Third-Party

![Icon](https://github.com/true-og/website/blob/main/assets/images/logos/Logo-Alternate-Transparent.png)

*ad astra per aspera*

Plugins used by TrueOG Network where the only changes we make are to the build scripts and config files. We also purge telemetry and log4j for security reasons. Any plugins with more comprehensive code changes than that belong in [Soft Forks](https://github.com/true-og/Soft-Forks).

See each individual submodule for relevant licenses. Nothing is more restrictive than GPLv3.

# All Third Party plugins should abide by the following standards, if applicable:

**Gradle 8.14.3:**

```./gradlew wrapper --gradle-version=8.14.3```

**Kotlin Gradle files:**

```build.gradle.kts, settings.gradle.kts```

**Shadow 8.3.8 from gradleup:**

```plugins { id("com.gradleup.shadow") version "8.3.8" }```

**[Paperweight API](https://docs.papermc.io/paper/dev/userdev/) 2.0.0-beta.17:**

```plugins { id("io.papermc.paperweight.userdev") version "2.0.0-beta.17" }```

**[Purpur API](https://repo.purpurmc.org/javadoc/snapshots/org/purpurmc/purpur/purpur-api/1.19.4-R0.1-SNAPSHOT/raw/index.html) 1.19.4:**

```dependencies { compileOnly("org.purpurmc.purpur:purpur-api:1.19.4-R0.1-SNAPSHOT") }```

**[LuckPerms API](https://luckperms.net/wiki/Developer-API) 5.5:**

```dependencies { compileOnly("net.luckperms:api:5.5") }```

**Shadow license into jars at the end of tasks.processResources:**

```
from("LICENSE") {
        into("/")
    } 
}
```

**Reproducible builds:**

```
tasks.withType<AbstractArchiveTask>().configureEach {
    isPreserveFileTimestamps = false
    isReproducibleFileOrder = true
}
```

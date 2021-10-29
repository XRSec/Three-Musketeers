# 三剑客

> [releases](https://github.com/XRSec/Three-Musketeers/releases) 那啥菜刀蚁剑都有客户端，so
## [Behinder](https://github.com/rebeyond/Behinder)

> Behinder需要 `openjfx` 支持，但是使用 `jpackage` 打包进去，并不会在运行的时候调用，所以先打包进目录，然后运行的时候调用

```bash
jpackage --name Behinder --input ./Behinder \
            --main-jar Behinder.jar \
            --type dmg  \
            --copyright "Behinder_v3.0 Beta 11【t00ls专版】.XRSec"  \
            --app-version "3.0" \
            --description "Behinder_v3.0 Beta 11【t00ls专版】" \
            --vendor "rebeyond" \
            --mac-package-name "Behinder" \
            --icon Behinder.icns \
            --java-options "-Dfile.encoding=utf-8 -XX:ParallelGCThreads=4  -XX:+AggressiveHeap -XX:+UseParallelGC --module-path \$APPDIR/lib --add-modules=javafx.controls --add-modules=javafx.fxml --add-modules=javafx.base --add-modules=javafx.graphics --add-modules=javafx.web"
```

## [Godzilla](https://github.com/BeichenDream/Godzilla)

> Godzilla 暂时不能使用 `jpackage` 进行打包，只能使用 `packr`

```bash
java -jar packr.jar Godzilla.json
```

```json
{
    "platform": "mac",
    "jdk": "jdk-17_macos-x64_bin.tar.gz",
    "executable": "Godzilla",
    "mainclass": "core.ui.MainActivity",
    "classpath": [
        "Godzilla.jar"
    ],
    "vmargs": [
        "Dfile.encoding=utf-8", 
        "ParallelGCThreads=4 ", 
        "AggressiveHeap", 
        "+UseParallelGC", 
        "Xms512M",
        "Xmx1024M"
    ],
    "output": "Godzilla.app",
    "icon": "Godzilla.icns"
}
```

## CobaltStrike

> 现在的 CobaltStrike 不能使用 `jpackage` 和 `packr` 打包，你们看看报错咋解决

```json
{
    "platform": "mac",
    "jdk": "jdk-17_macos-x64_bin.tar.gz",
    "executable": "CobaltStrike",
    "mainclass": "aggressor.Aggressor",
    "classpath": [
        "cobaltstrike.jar"
    ],
    "vmargs": [
        "Dfile.encoding=utf-8", 
        "ParallelGCThreads=4 ", 
        "AggressiveHeap", 
        "+UseParallelGC", 
        "Xms512M",
        "Xmx1024M",
        "javaagent:hook.jar",
        "javaagent:cobaltstrikecn.jar"
    ],
    "output": "CobaltStrike.app",
    "resources": [
        "CobaltStrike/cobaltstrikecn.jar",
        "CobaltStrike/Ladon9.0",
        "CobaltStrike/hook.jar"
    ],
    "icon": "cobaltstrike.icns"
}
```

```bash
jpackage --name CobaltStrike --input ./CobaltStrike \
  --main-jar cobaltstrike.jar \
  --type dmg  \
  --copyright "CobaltStrike_v4.4 .XRSec"  \
  --app-version "4.4" \
  --description "CobaltStrike_v4.4 .XRSec" \
  --mac-package-name "CobaltStrike" \
  --icon cobaltstrike.icns \
  --java-options "-Dfile.encoding=utf-8 -XX:ParallelGCThreads=4  -XX:+AggressiveHeap -XX:+UseParallelGC -javaagent:\$APPDIR/hook.jar -javaagent:\$APPDIR/cobaltstrikecn.jar"
```

> XRSec has the right to modify and interpret this article. If you want to reprint or disseminate this article, you must ensure the integrity of this article, including all contents such as copyright notice. Without the permission of the author, the content of this article shall not be modified or increased or decreased arbitrarily, and it shall not be used for commercial purposes in any way

---
layout: default
title: "Setup"
---

<img src="/setup/intellij.svg" width="160" height="160" />
<img src="/setup/gradle.svg" width="160" height="160" />

KorGE game engine uses [intelliJ IDEA Community or Ultimate](https://www.jetbrains.com/idea/download/) as IDE and [Gradle](https://gradle.org/) as building tool. Korge provides [plugins for both](/plugin) in order to generate all the required preprocessed resources.

### Setup intelliJ

> You have to visit [https://www.jetbrains.com/idea/download/](https://www.jetbrains.com/idea/download/), and download an intelliJ IDEA IDE, either Community or Ultimate will work. Community is free, but Ultimate has tons of additional features, and allows you to use it as a really polyglot IDE.

![](/setup/download.png)

> After installing and launching, you have to go to `Configure -> Plugins`

![](/setup/plugins.png)

> Then click the `Browse repositories...` button.

![](/setup/browse_repositories.png)

> Then search for `Korge` and click the `Install` green button. That will suggest you to restart the IDE. Do so.

![](/setup/korge_plugin.png)

> After that, you should see the Korge menu when opening a project.
> Depending on the version you will see `Korge` it in the main menu or in the `Tools -> Korge` menu.

![](/setup/korge_plugin_menu.png)

> Korge will work on projects that include `korge-core` artifact.

### Supported Artifacts

* `com.soywiz:korge:$korVersion`
* `com.soywiz:korge-ext-swf:$korVersion`
* `com.soywiz:korge-ext-particle:$korVersion`
* `com.soywiz:korge-ext-spriter:$korVersion`
* `com.soywiz:korge-ext-tiled:$korVersion`
* `com.soywiz:korge-ext-lipsync:$korVersion`

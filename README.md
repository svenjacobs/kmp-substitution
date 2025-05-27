Example project reproducing the KMP Gradle dependency substitution bug.

[lib](./lib) is a KMP library and [app](./app) is an Android application.
`app` includes `lib` in its [settings.gradle.kts](./app/settings.gradle.kts)
and substitutes the `my.example.library:library` dependency with `lib/library`.

Compilation works from the terminal but opening `app` in Android Studio produces
the following error in the Sync window:

```
Expected android module not found! /Users/sven/Developer/Workspace/kmp-substitution/app::library
```

Can be reproduced with **Android Studio Meerkat Feature Drop | 2024.3.2** (AGP `8.10.0`) 
as well as **Android Studio Narwhal Feature Drop | 2025.1.2 Canary 2** (AGP `8.12.0-alpha02`).
Gradle version is `8.14.1`.

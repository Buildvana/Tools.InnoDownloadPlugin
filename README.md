**Q:** What is this package?

**A:** This package contains [Mitrich Software's Inno Download Plugin](https://mitrichsoftware.wordpress.com/) in its entirety, source code included.

**Q:** Isn't there already [Tools.InnoSetup.Download](https://www.nuget.org/packages/Tools.InnoSetup.Download/) by [J Wyman](https://github.com/whoisj) that does the same?

**A:** While the contents of the two packages are practically the same, this package also defines a MSBuild property `InnoDownloadPluginDir` containing the full path (without a trailing backslash) to the directory where `idp.iss` is located.

**Q:** The NuGet client will already create a `PkgTools_InnoDownloadPlugin` property for that. What's the point of having one more property?

**A:** NuGet's `Pkg_*` properties are only available during "inner" builds, i.e. when the `TargetFramework` property is available. `InnoDownloadPluginDir` is always available: for example, you cannot use `PkgTools_InnoDownloadPlugin` in a `Pack` target, but you can use `InnoDownloadPluginDir`. As a matter of fact, this package was created specifically to integrate Inno Download Plugin in the "alternate Pack" feature of [Buildvana SDK](https://github.com/Buildvana/Buildvana.Sdk).

---

Inno Download Plugin is Copyright (c) 2013-2015 [Mitrich Software](https://mitrichsoftware.wordpress.com/).

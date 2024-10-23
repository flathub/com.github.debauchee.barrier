# com.github.debauchee.barrier

## How to build

1. Clone repo with submodules: `git clone --recursive git@github.com:flathub/com.github.debauchee.barrier.git`
2. Install flatpak-builder, i.e: `dnf install flatpak-builder`
3. Install corresponding runtime and SDK, i.e.: `flatpak install org.kde.Sdk/x86_64/5.15-23.08` `flatpak install org.kde.Platform/x86_64/5.15-23.08`
4. Build by executing: `flatpak-builder build com.github.debauchee.barrier.json --force-clean`

   - if you encounter an issue `fatal: transport 'file' not allowed` during build execute `git config --global --add protocol.file.allow always` to fix it:

     ```bash
     Cloning into '/home/user/com.github.debauchee.barrier/.flatpak-builder/build/barrier-10/ext/gtest'...
     fatal: transport 'file' not allowed
     fatal: clone of 'file:///home/user/com.github.debauchee.barrier/.flatpak-builder/git/https_github.com_google_googletest.git' into submodule path '/home/user/com.github.debauchee.barrier/.flatpak-builder/build/barrier-10/ext/gtest' failed
     ```

5. Install a build: `flatpak-builder --user --install --force-clean build com.github.debauchee.barrier.json`
6. Test the build: `flatpak run com.github.debauchee.barrier`

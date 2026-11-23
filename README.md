<img width="900" height="383" alt="封面图" src="https://github.com/user-attachments/assets/1e0fc4af-e7a9-43f7-bdd9-53d738330775" />


# DroidDeck: Run PC Games Locally on Android Without Streaming

> Originally published on [LIZHI.SHOP](https://lizhi.shop/en/articles/droiddeck-run-pc-games-android?cid=53qvofdc&utm_source=lizhi-shop&utm_medium=github)

Modern mobile hardware has grown capable enough to repurpose retired or idle Android devices into dedicated portable gaming handhelds. **DroidDeck** is an open-source solution that allows an Android device to **run locally** Windows PC titles from major digital distribution storefronts such as Steam, Epic Games, and GOG.

TL;DR: DroidDeck (Local PC Runner) + Snapdragon Device + Steam / Epic / GOG Library + Controller.

| Tool | What it does | Notes |
| :--- | :--- | :--- |
| DroidDeck | Executes Windows PC games locally on Android | Uses Proton and FEX translation; requires Qualcomm Adreno GPUs |
| nvidia-macos-driver | Enables NVIDIA graphics cards on macOS | Supports GTX 16 through RTX 50 series |
| Maclator | Executes ARM applications on Intel-based Macs | Functions as a reverse Rosetta layer |

## DroidDeck: Architecture and Setup for Local PC Gaming

Unlike remote play solutions such as Moonlight or cloud services like GeForce NOW, DroidDeck is **not streaming, and not cloud gaming**; it executes game binaries directly on device hardware. The application bridges the platform gap by combining the Proton compatibility layer with FEX instruction translation, which dynamically converts x86 machine instructions into ARM instructions compatible with mobile processors.

<img width="1200" height="900" alt="图 1" src="https://github.com/user-attachments/assets/c42588d4-187f-4b81-91d3-52d319448008" />


A key advantage of DroidDeck is accessibility: there is **no Root required, and no custom ROM flashing either**. The software does not provide game files; users sign in to their existing platforms to install and run the genuine copies they already own. The installation package is distributed as an APK through GitHub Releases, allowing users to audit the code base directly. The interface natively **supports Chinese** alongside standard localizations.

Initial setup requires a one-time configuration via standard Android developer features:

1. Navigate to Android system settings and enable Developer options.
2. Turn on wireless debugging under Developer options.
3. Complete the ADB pairing process directly on the device.

Once this pairing handshake succeeds, configuration remains persistent across restarts—there is **no need to go through it all again** on subsequent launches. Users can then log in to **Steam**, **Epic**, or GOG accounts to manage their game libraries.

<img width="2000" height="900" alt="图 4" src="https://github.com/user-attachments/assets/67bd676a-0e25-40af-b4e7-9cf22b58bef3" />


Input handling accommodates multiple configurations. DroidDeck detects both Bluetooth and wired USB controllers out of the box. For users without physical accessories, the client **comes with on-screen virtual buttons** with customizable layouts.

## Performance Benchmarks and Hardware Limitations

Actual gameplay performance depends heavily on the device's system-on-chip (SoC) and graphical architecture. Entry-level hardware such as the Qualcomm Snapdragon 768G can handle lightweight indie titles, but 3D releases require substantial processing headroom.

The project officially recommends an Adreno 730 GPU or higher, translating to **Snapdragon 8 Gen 1 or newer** platforms as the practical baseline. While modern high-end chips can launch demanding titles such as Black Myth: Wukong, real-world frame rates fluctuate. Testing on a Snapdragon 8 Elite device running Cyberpunk 2077 at 720p with medium settings demonstrated frame rates between 40 and 60 fps. Because instruction translation incurs significant CPU and GPU overhead, heavy AAA titles cannot maintain perfectly locked performance.

<img width="2000" height="900" alt="图 7" src="https://github.com/user-attachments/assets/e3d6b71e-d158-44ea-801a-121279b80150" />


Hardware compatibility is currently restricted to devices equipped with a **Qualcomm Adreno GPU**. Smartphones or tablets powered by MediaTek Dimensity, Samsung Exynos, or Google Tensor chipsets are currently unsupported due to driver and translation requirements. In addition, because modern phone displays feature non-standard widescreen aspect ratios, in-game user interfaces and subtitle typography may appear miniature; players can mitigate this by adjusting internal render scales or selecting "TV" interface scaling inside individual game settings.

## Cross-Platform Open-Source Utilities

DroidDeck is **free and open source**, fully self-contained for local execution, and **easy to pick up** without extra hardware purchases. For users seeking productivity software alongside gaming utilities, genuine licenses with verified distribution are cataloged on [LIZHI.SHOP](https://lizhi.shop/?cid=53qvofdc&utm_source=lizhi-shop&utm_medium=github).

Related open-source hardware translation projects have emerged alongside local mobile emulation:

- An open-source **NVIDIA graphics driver** for macOS brings driver compatibility for modern discrete GPUs ranging from GTX 16 series up to RTX 50 series hardware.
- Maclator provides a translation layer designed to execute ARM-native macOS applications on legacy Intel Macs, bridging compatibility as modern software drops x86-64 support.

## Summary

> [!TIP]
> - DroidDeck runs Windows PC titles natively on Android via Proton and FEX without requiring Root access or system flashing.
> - Hardware compatibility is strictly limited to Qualcomm Snapdragon devices with Adreno GPUs, with Snapdragon 8 Gen 1 or newer recommended.
> - Games must be owned and downloaded directly through personal Steam, Epic, or GOG accounts.

## Credits

Written by the LIZHI.SHOP editorial team, first published on [LIZHI.SHOP](https://lizhi.shop/en/articles/droiddeck-run-pc-games-android?cid=53qvofdc&utm_source=lizhi-shop&utm_medium=github) on 2026-10-15

## Reference

- [DroidDeck on GitHub](https://github.com/Droid-Deck/DroidDeck?utm_source=lizhi-shop)
- [NVIDIA macOS Driver on GitHub](https://github.com/nullmoth/nvidia-macos-driver?utm_source=lizhi-shop)


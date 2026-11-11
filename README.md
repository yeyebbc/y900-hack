# y900-hack

Research notes for unofficial bootloader unlocking on the **Lenovo Legion Y900 13 (TB522FU)**.

## Status — 2026-11-11

The investigated tablet runs Android 17 / ZUX OS 2.5.10.028 on a Qualcomm SM8750P. Its bootloader remains locked, and Android reports green verified boot. A working unofficial unlock procedure for this exact firmware has **not** been established.

A previous attempt using a locally generated NekoYuzu ZUX token completed the upload but returned `oem unlock fail, OTHERS` at the unlock step. Upload success does not establish that the token passed validation.

## Files

- [unlock-investigation.txt](unlock-investigation.txt): observed device state, previous failure, tool inspection, source links, and remaining technical prerequisites.
- [使用指南.md](使用指南.md): supplied GeekFlashTool usage guide, retained as third-party reference material.
- [使用指南-腾讯文档.txt](使用指南-腾讯文档.txt): original online guide link.
- [匣(0.5.24.1031-A).7z](<匣(0.5.24.1031-A).7z>): supplied GeekFlashTool archive, preserved unchanged.
- [viQOO工具箱V3.0.0by某贼.7z](viQOO工具箱V3.0.0by某贼.7z): supplied viQOO toolbox archive, preserved unchanged.

## Findings

- The supplied viQOO V3.0.0 unlock routine attempts a vendor-image flash followed by a vivo-specific command. It is not an established Lenovo TB522FU method.
- GeekFlashTool provides low-level flashing functions, but this investigation did not verify a TB522FU unlock procedure in it. Live interface inspection was limited by Windows capture failures.
- [lapiSwitch's TB522FU configuration](https://github.com/corrupt3904/lapiSwitch/blob/main/devices/TB522FU/device.toml) currently enables DeviceInfo reads and disables writes pending validation. A dump workflow can still involve temporary partition changes; it is not automatically a read-only device operation.

These are dated investigation results, not a flashing tutorial. Upstream support and firmware behavior can change.

The original tool archives are tracked so a clone includes the tools used in this investigation. Archive SHA-256 values are recorded in [unlock-investigation.txt](unlock-investigation.txt). Extracted working copies under `inspection/`, standalone firmware images, device backups, unlock tokens, logs, and the original conversation export remain local and are excluded from Git. Device-specific identifiers are not needed to reproduce the research. Third-party tools and reference material retain their authors' rights.

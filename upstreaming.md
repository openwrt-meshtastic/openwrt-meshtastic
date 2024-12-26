# Upstreaming Status

Status of efforts to upstream `meshtasticd`, `python-meshtastic`, and their dependencies into [`openwrt/packages`](https://github.com/openwrt/packages).

For the most up to date status see [vidplace7's `openwrt/packages` PRs](https://github.com/openwrt/packages/pulls?q=author%3Avidplace7).

We plan to target `master`, `openwrt-24.10` and (later) `openwrt-23.05` for LibreMesh / AREDN compatibility.

#### Legend
📥 PR Submitted

✅ PR Merged

🕰️ Waiting for another PR

📑 To-do (need to submit)


## `meshtasticd`

### New Packages
| Package             | `master`     | `openwrt-24.10` | `openwrt-23.05` | Notes
| :------------------ | :----------: | :-------------: | :-------------: | :----
| libyder             | [✅][#25503] | 📑              |                 |
| **meshtasticd**     | 📑 🕰️        |                 |                 | Pending Beta release with CH341 fixes
| **meshtasticd-web** | 📑 🕰️        |                 |                 |
| python-platformio   | [✅][#25528] | 📑              |                 |
| python-pyelftools   | [✅][#25502] | 📑              |                 |
| python-tabulate     | [✅][#25501] | 📑              |                 | Also used in `python-meshtastic`

[#25503]: https://github.com/openwrt/packages/pull/25503
[#25528]: https://github.com/openwrt/packages/pull/25528
[#25502]: https://github.com/openwrt/packages/pull/25502
[#25501]: https://github.com/openwrt/packages/pull/25501

### Modified Packages
| Package         | `master`     | `openwrt-24.10` | `openwrt-23.05` | Notes
| :-------------- | :----------: | :-------------: | :-------------: | :----
| liborcania      | [✅][#25526] | 📑              |                 | Install library on target
| libulfius       | [✅][#25527] | 📑              |                 | Install library on target
| python-certifi  | [✅][#25497] | [📥][#25542]    |                 | Add hostbuild
| python-chardet  | [✅][#25496] | [📥][#25542]    |                 | Add hostbuild
| python-click    | [✅][#25492] | 📑              |                 | Add hostbuild
| python-idna     | [✅][#25498] | [📥][#25542]    |                 | Add hostbuild
| python-pyserial | [✅][#25494] | 📑              |                 | Add hostbuild
| python-requests | [✅][#25499] | [📥][#25542]    |                 | Add hostbuild
| python-urllib3  | [✅][#25495] | [📥][#25542]    |                 | Add hostbuild

[#25526]: https://github.com/openwrt/packages/pull/25526
[#25527]: https://github.com/openwrt/packages/pull/25527
[#25497]: https://github.com/openwrt/packages/pull/25497
[#25496]: https://github.com/openwrt/packages/pull/25496
[#25492]: https://github.com/openwrt/packages/pull/25492
[#25498]: https://github.com/openwrt/packages/pull/25498
[#25494]: https://github.com/openwrt/packages/pull/25494
[#25499]: https://github.com/openwrt/packages/pull/25499
[#25495]: https://github.com/openwrt/packages/pull/25495

[#25542]: https://github.com/openwrt/packages/pull/25542


## `python-meshtastic`

### New Packages
| Package               | `master`     | `openwrt-24.10` | `openwrt-23.05` | Notes
| :-------------------- | :----------: | :-------------: | :-------------: | :----
| abseil-cpp            | [✅][#25565] | 📑 🕰️           |                 | Dep for *updating* `protobuf`
| python-dotmap         | 📑           |                 |                 | Optional
| **python-meshtastic** | 🕰️           |
| python-print-color    | 📑           |                 |                 | Optional
| python-protobuf       | 📑 🕰️        |                 |                 | Awaiting `protobuf` update.
| python-pypubsub       | [✅][#25576] | 📑              |                 |
| python-pyqrcode       | 📑           |                 |                 | Optional

[#25565]: https://github.com/openwrt/packages/pull/25565
[#25576]: https://github.com/openwrt/packages/pull/25576

### Modified Packages
| Package  | `master`        | `openwrt-24.10` | `openwrt-23.05` | Notes
| :------- | :-------------: | :-------------: | :-------------: | :----
| node     | [🕰️ 📥][#25582] |                 |                 | Fix compile after `abseil-cpp` addition in [openwrt/packages#25565][#25565]
| protobuf | [📥][#25566]    |                 |                 | Depends on `abseil-cpp`

[#25582]: https://github.com/openwrt/packages/pull/25582
[#25566]: https://github.com/openwrt/packages/pull/25566

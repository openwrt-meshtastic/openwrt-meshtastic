# Upstreaming Status

Status of efforts to upstream `meshtasticd` and it's dependencies into [`openwrt/packages`](https://github.com/openwrt/packages).

For the most up to date status see [vidplace7's `openwrt/packages` PRs](https://github.com/openwrt/packages/pulls?q=author%3Avidplace7).

#### Legend
📥 PR Submitted

✅ PR Merged

🕰️ Waiting for another PR

📑 To-do (need to submit)


## `meshtasticd`

### New Packages
| Package             | `master`        | `openwrt-24.10` | `openwrt-23.05` | Notes
| :------------------ | :-------------: | :-------------: | :-------------: | :----
| libyder             | [📥 🕰️][#25503] |                 |                 | Awaiting liborcania modification
| **meshtasticd**     | 🕰️              |                 |                 | Awaiting python-platformio
| **meshtasticd-web** | 🕰️              |                 |                 |
| python-platformio   | [📥 🕰️][#25528] |                 |                 | Awaiting python-[tabulate,pyelftools,click,pyserial,~~requests~~] hostbuild modifications
| python-pyelftools   | [📥][#25502]    |                 |                 |
| python-tabulate     | [📥][#25501]    |                 |                 | Also used in `python-meshtastic`

[#25503]: https://github.com/openwrt/packages/pull/25503
[#25528]: https://github.com/openwrt/packages/pull/25528
[#25502]: https://github.com/openwrt/packages/pull/25502
[#25501]: https://github.com/openwrt/packages/pull/25501

### Modified Packages
| Package         | `master`        | `openwrt-24.10` | `openwrt-23.05` | Notes
| :-------------- | :-------------: | :-------------: | :-------------: | :----
| liborcania      | [📥][#25526]    |                 |                 | Install library on target
| libulfius       | [📥 🕰️][#25527] |                 |                 | Install library on target // Awaiting liborcania modification
| python-certifi  | [✅][#25497]    | [📥][#25542]    |                 | Add hostbuild
| python-chardet  | [✅][#25496]    | [📥][#25542]    |                 | Add hostbuild
| python-click    | [📥][#25492]    |                 |                 | Add hostbuild
| python-idna     | [✅][#25498]    | [📥][#25542]    |                 | Add hostbuild
| python-pyserial | [📥][#25494]    |                 |                 | Add hostbuild
| python-requests | [✅][#25499]    | [📥][#25542]    |                 | Add hostbuild
| python-urllib3  | [✅][#25495]    | [📥][#25542]    |                 | Add hostbuild

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
| Package               | `master`        | `openwrt-24.10` | `openwrt-23.05` | Notes
| :-------------------- | :-------------: | :-------------: | :-------------: | :----
| python-dotmap         | 📑
| **python-meshtastic** | 🕰️
| python-pexpect        | 📑
| python-print-color    | 📑
| python-protobuf       | 📑
| python-pypubsub       | 📑
| python-pyqrcode       | 📑
| python-webencodings   | 📑

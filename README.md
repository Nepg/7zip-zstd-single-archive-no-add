# 7zip-zstd-single-archive-no-add

一个修改版 7zip-zstd Shell 扩展：在资源管理器中只选中 1 个压缩包文件时，隐藏右键菜单中的压缩相关项。

## 这是什么

官方 7-Zip 在选中单个压缩包（如 `.zip`、`.7z`）时，右键菜单仍会显示：

- 添加到压缩包
- 添加到 "xxx.7z"
- 添加到 "xxx.zip"

本项目基于 7-Zip-zstd 源码，修改了 Shell 扩展的菜单显示逻辑，修改了 Shell 扩展的菜单显示逻辑：当只选中 1 个文件，且该文件扩展名属于压缩包时，不插入上述菜单项。

这是对默认行为的定制修改，不是官方发布。

## 修改内容

- 仅选中 1 个压缩包文件时，隐藏压缩相关菜单项。

## 不变的情况

- 选中多个文件
- 选中单个非压缩包文件（含 `.exe`、`.msi`）
- 选中文件夹
- 解压、打开、编辑等菜单
- 7-Zip 主程序功能

## 支持的压缩包扩展名

`.7z` `.zip` `.rar` `.tar` `.gz` `.bz2` `.xz` `.cab` `.iso` `.tgz` `.tbz2` `.lzma` `.arj` `.lzh` `.z` `.cpio`

## 安装

1. 从 [Releases](https://github.com/Nepg/7zip-zstd-single-archive-no-add/releases) 下载 `7zip-zstd-single-archive-no-add-v1.0.zip`。
2. 解压。
3. 关闭所有资源管理器窗口。
4. 右键 `replace.bat` → 以管理员身份运行。
5. 脚本会先备份原文件到 `7-zip.dll.bak`，再替换 `7-zip.dll`。
6. 若提示需要重启，重启后生效。

## 回滚

如需撤销替换，右键 `rollback.bat` → 以管理员身份运行。
脚本会从 `7-zip.dll.bak` 恢复原文件。

## 说明

- 仅 x64。
- 基于 7-Zip-zstd 源码修改，非官方发布。
- 默认安装路径为 `C:\Program Files\7-Zip-Zstandard\`。
- 备份文件 `7-zip.dll.bak` 只创建一次，如果已存在，`replace.bat` 不会覆盖它。
- 替换前请自行确认路径并备份。

---

# 7zip-zstd-single-archive-no-add

A modified 7zip-zstd extension: hides compress-related context menu items when exactly one archive file is selected in Explorer.

## What is this

Official 7-Zip still shows the following context menu items when a single archive file (e.g. `.zip`, `.7z`) is selected:

- Add to archive
- Add to "xxx.7z"
- Add to "xxx.zip"

This project modifies the Shell extension menu logic based on the 7-Zip ZS source: when exactly one file is selected and its extension belongs to an archive format, those menu items are not inserted.

This is a deliberate customization of the default behavior, not an official release.

## Modification

- When exactly one archive file is selected, compress-related menu items are hidden.

## Unchanged cases

- Multiple files selected
- Single non-archive file (including `.exe`, `.msi`)
- Single folder
- Extract, open, edit and other menu items
- 7-Zip main program functionality

## Supported archive extensions

`.7z` `.zip` `.rar` `.tar` `.gz` `.bz2` `.xz` `.cab` `.iso` `.tgz` `.tbz2` `.lzma` `.arj` `.lzh` `.z` `.cpio`

## Install

1. Download `7zip-zstd-single-archive-no-add-v1.0.zip` from [Releases](https://github.com/Nepg/7zip-zstd-single-archive-no-add/releases).
2. Extract.
3. Close all Explorer windows.
4. Right-click `replace.bat` → Run as administrator.
5. The script backs up the original file to `7-zip.dll.bak`, then replaces `7-zip.dll`.
6. If prompted, reboot to apply.

## Rollback

To undo the replacement, right-click `rollback.bat` → Run as administrator.
The script restores `7-zip.dll` from `7-zip.dll.bak`.

## Notes

- x64 only.
- Modified build based on 7-Zip ZS source, not an official release.
- Default install path is assumed to be `C:\Program Files\7-Zip-Zstandard\`.
- The backup file `7-zip.dll.bak` is only created once. If it already exists, `replace.bat` will not overwrite it.
- Please verify the path and back up before replacing.

## License

Based on 7-Zip ZS source. Follow the original 7-Zip license
(GNU LGPL / BSD / unRAR restriction) and the licenses of the
bundled codecs (Zstandard, Brotli, LZ4, etc.).

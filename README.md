# VPB Mesh Loader – Update Checker

This repository only hosts the update information for **VPB Mesh Loader**
(a client-side addon for Vic's Point Blank that loads Blockbench poly_mesh models).

On startup, VPB Mesh Loader reads
`https://raw.githubusercontent.com/VellEagle/VPBMeshLoader-Update-Checker/main/update.json` once.
If a newer version exists for the player's platform, the title screen asks whether to open the download page.
Nothing is downloaded or installed automatically, and no player data is sent.
Players can turn the check off with `checkForUpdates=false` in `config/vpbmeshloader-update.properties`.

---

# VPB Mesh Loader 更新情報（日本語）

このリポジトリには、VPB Mesh Loader の更新情報（`update.json`）だけを置いています。Mod のソースコードはありません。

VPB Mesh Loader は起動時に上の URL を 1 回だけ読み、自分の環境向けの `latest` が今の版より新しければ、
タイトル画面で「ダウンロードページを開きますか？」と表示します（ダウンロードや入れ替えはしません）。

## 新しい版を出したとき
1. jar を CurseForge（https://www.curseforge.com/minecraft/mc-mods/vpb-mesh-loader ）に公開する
2. `update.json` の該当する環境の `latest` を新しい版番号に、`url` をそのダウンロードページに書き換える
3. `changelog` に短い説明（英語推奨・1〜2行）を書くと、通知画面に表示される

| キー | 対象 |
|---|---|
| forge-1.20.1 | Forge 1.20.1 版 |
| neoforge-1.21.1 | NeoForge 1.21.1 版 |
| fabric-1.21.1 | Fabric 1.21.1 版 |
| neoforge-26.1.2 | NeoForge 26.1.2 版 |
| fabric-26.1.2 | Fabric 26.1.2 版 |

- 各 Mod は**自分の環境の欄だけ**を読みます。1 つの環境だけ更新すれば、その環境の利用者にだけ通知が出ます。
- 版番号は Mod 側の版と同じ形式（例: `0.2.0`）で書いてください。
- 書き換えで `,` や `"` を消すなど JSON の書き方を間違えると、全環境で通知が出なくなります（ゲームには影響しません）。
  保存前に https://jsonlint.com などで確認すると安心です。

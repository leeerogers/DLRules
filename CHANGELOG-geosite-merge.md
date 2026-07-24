# 规则合并 Changelog — geosite 增量并入 DLRules

**日期**：2026-07-24
**来源**：MetaCubeX `meta-rules-dat`（geosite `.list`），Apple 用本地完整源
**范围**：Clash `Clash/Provider/**.yaml` + Surge `Surge/Surge 3/Provider/**.list`，每类两份同步
**方法**：geosite domain-set（`+.`/前导`.`=后缀，裸域名=精确）转 classical；与现有规则**双向去重**（新条目被旧后缀覆盖、旧精确被新后缀覆盖都剔除），并清理原文件历史重复；每份产出做 YAML/语法合法性 + 零重复零冗余校验。原有规则保留，新增追加在文件末尾注释块内。

## 各分类新增

| 分类 | 新增(后缀/精确) | 清理旧重复 |
|---|---|---|
| AI Suite | +116 (95/21) | 3 |
| YouTube | +15 (14/1) | — |
| Netflix | +17 (16/1) | — |
| Disney Plus | +149 (146/3) | — |
| Spotify | +22 (14/8) | — |
| Apple TV+ | +4 (0/4) | — |
| Apple | +1571 (1523/48) | — |
| Telegram | +8 (8/0) | — |
| TikTok | +29 (24/5) | — |
| Microsoft | +35 (25/10) | 19 |
| Crypto | +143 (135/8) | 11 |
| PayPal | +244 (243/1) | — |
| Discord | +22 (20/2) | — |
| Steam | +53 (35/18) | — |
| Speedtest | +12 (11/1) | — |
| Douyin | +67 (67/0) | — |
| Bilibili | +43 (43/0) | 1 |
| IQIYI | +0 | 1 |
| Youku | +7 (7/0) | — |
| Netease Music | +48 (48/0) | 9 |
| Amazon (Prime Video) | +15 (10/5) | — |
| BBC iPlayer | +24 (9/15) | — |
| DAZN | +3 (3/0) | — |
| Hulu | +43 (42/1) | — |
| Bahamut | +1 (1/0) | 1 |
| Abema TV | +10 (9/1) | 1 |
| Niconico | +1 (1/0) | 1 |

**合计**：27 个分类、约 2700 条新规则（Google FCM 现有已全覆盖，未改）。

## 未处理（无干净 geosite 源）

- **Tencent Video** — geosite 只有过宽的全站 `tencent`，无视频专用源
- **WeTV** — geosite 404
- **Max** — geosite 404
- 冷门项（encoreTVB、Japonx、JOOX、KKBOX、KKTV、Letv、Line TV、MOO、myTV SUPER、ViuTV、ABC、F1 TV、Fox Now、Fox+、Discovery Plus、PBS、Pandora、Pornhub、Soundcloud、Hulu Japan、Apple Music、Apple News 等）— 多数无对应 geosite 源，未动

## 建议 commit message

```
rules: 并入 geosite 增量到 27 个分类 (Clash+Surge)

来源 MetaCubeX geosite；双向去重 + 清理历史重复；约 +2700 条。
详见 CHANGELOG-geosite-merge.md。
```

# liquid-geo-temple 主題計畫

## 目標

為 `dynamic-wallpaper` 新增原創動態桌布主題 `liquid-geo-temple`。主題以受局部重力操縱的實體碳粒子為核心：粒子從靜置的六角沙床聚合成精密、可見縫隙的三維重力浮雕，經過正午平衡與傍晚過載後，在午夜回到沉積狀態。

參考只用於抽取「觸覺式微粒浮雕、持續變形、古文明與先進重力工程的張力」等設計原理；不得重製任何既有作品的角色、家徽、文字、場景、鏡頭、logo 或可識別資產。

## Repo 契約

`dwall.sh` 依目前小時讀取 `images/<style>/<hour>.jpg` 或 `.png`。本主題將建立 `images/liquid-geo-temple/`，提供完整 `0.jpg` 到 `23.jpg`：

- 12 張實體 JPG：`0.jpg`、`2.jpg`、`4.jpg`、`6.jpg`、`8.jpg`、`10.jpg`、`12.jpg`、`14.jpg`、`16.jpg`、`18.jpg`、`20.jpg`、`22.jpg`
- 12 個相對 symlink：每個奇數小時連至前一個偶數主圖
- 每張主圖目標為 `3840x2160`、16:9、sRGB、JPG
- 不修改 `dwall.sh`、`install.sh`、`test.sh` 或桌面環境設定

## 美術方向

- **構圖：** 核心主體固定於畫面中央約 45% 寬度；兩側為深黑曜石至石墨灰的低細節留白，適合桌面圖示、視窗與雙螢幕裁切。
- **材質：** 黑曜石、深石墨、黑鐵、槍灰、灰銀與少量埋藏於接縫的青銅。碳粒子是啞光、帶重量的微型六角實體，而不是光點、液晶或全息投影。
- **科技語言：** 使用同心軌道、分段承載環、六角晶格、重力匯流線與有精密誤差的粒子群；古老感只保留在青銅底材與深層接縫。
- **用色節奏：** 午夜至清晨採霜藍與灰銀；日間是黑鐵、槍灰與冷白高光；傍晚只在接縫、重力井使用克制的琥珀與暗紅反射。
- **禁止內容：** 人物、臉孔、衣飾、既有家徽、文字、可讀 UI、螢幕、商標、真實星圖、現成電影構圖、強烈霓虹、火焰、血腥或怪物。

## 小時敘事與檔案映射

| 時段 | 實體主圖 | 畫面 |
|---|---|---|
| `00-01` | `0.jpg` | 靜置源床：霜藍側光掠過灰銀粒子床，中央半埋黑鐵環。 |
| `02-03` | `2.jpg` | 測繪脈絡：無文字六角測繪紋、三條重力導線與冷藍邊光。 |
| `04-05` | `4.jpg` | 環門甦醒：分段環由粒子床升起，接縫露出極少量氧化青綠。 |
| `06-07` | `6.jpg` | 垂直檔案庫：同心軌道升成精密浮雕門廊，背景維持黑曜石負空間。 |
| `08-09` | `8.jpg` | 城市拓撲：抽象階梯城市地形與微型承載塔，光色轉為中性灰銀。 |
| `10-11` | `10.jpg` | 星圖匯流：非真實星點與交疊圓軌聚成黑鐵核心輪廓。 |
| `12-13` | `12.jpg` | 正午重力聖殿：核心完整懸浮，六角格、分段環與粒子瀑布精密平衡。 |
| `14-15` | `14.jpg` | 重量轉移：核心形成受控的偏心機械弧帶，以灰銀高光拉出深度。 |
| `16-17` | `16.jpg` | 過載承載環：結構完整但接縫開始反射少量琥珀，粒子流速感增加。 |
| `18-19` | `18.jpg` | 失衡協議：中心環局部斷續，暗紅只存在於少數重力井與接縫。 |
| `20-21` | `20.jpg` | 塌縮漩渦：沉重粒子向下回落成帶誤差的黑色旋渦，光線幾乎被吞沒。 |
| `22-23` | `22.jpg` | 餘波沉積：回到霜藍灰銀粒子床，只遺留半埋核心弧與零星青銅底材。 |

Symlink：

- `1.jpg` -> `0.jpg`
- `3.jpg` -> `2.jpg`
- `5.jpg` -> `4.jpg`
- `7.jpg` -> `6.jpg`
- `9.jpg` -> `8.jpg`
- `11.jpg` -> `10.jpg`
- `13.jpg` -> `12.jpg`
- `15.jpg` -> `14.jpg`
- `17.jpg` -> `16.jpg`
- `19.jpg` -> `18.jpg`
- `21.jpg` -> `20.jpg`
- `23.jpg` -> `22.jpg`

## 生成與驗收

1. 使用固定的共同提示描述材質、中央核心、左右留白與原創限制，再加入該時段的場景變數；每次只生成一張主圖。
2. 每次生成後，先在本機檔案系統確認本批新圖檔存在，再裁切／縮放、輸出最終 JPG 或複製到 `images/liquid-geo-temple/`。聊天預覽不能視為產出成功。
3. 主圖完成後才建立 symlink，並確認所有 `0-23.jpg` 都存在、連結目標正確、檔案為 16:9 且可由標準影像工具讀取。
4. 採非侵入式驗證；除非使用者明確要求，不執行會變更目前桌布的 `./test.sh -s liquid-geo-temple`。

```bash
find images/liquid-geo-temple -maxdepth 1 \( -type f -o -type l \) -name '*.jpg' | wc -l
find images/liquid-geo-temple -maxdepth 1 -type f -name '*.jpg' | wc -l
find images/liquid-geo-temple -maxdepth 1 -type l -name '*.jpg' -printf '%f -> %l\n' | sort -V
identify -format '%f %wx%h\n' images/liquid-geo-temple/*.jpg | sort -V
./test.sh -h | rg 'liquid-geo-temple|Available styles'
git diff --check
```

## 參考依據

- [氪星（維基百科）](https://zh.wikipedia.org/zh-tw/%E6%B0%AA%E6%98%9F)：抽取「高度先進文明與環境崩解」的敘事張力。
- [《超人：鋼鐵英雄》（維基百科）](https://zh.wikipedia.org/wiki/%E8%B6%85%E4%BA%BA%EF%BC%9A%E9%8B%BC%E9%90%B5%E8%8B%B1%E9%9B%84)：抽取重力改造與世界引擎般的宏觀動力意象。
- [WIRED：Designing Krypton's Tech Effects](https://www.wired.com/video/watch/design-fx-man-of-steel-designing-krypton-s-tech-effects-exclusive)：抽取觸覺式微粒、形體持續變化與照明的重要性。
- [The Art of VFX：Dan Lemmon 訪談](https://www.artofvfx.com/man-of-steel-dan-lemmon-vfx-supervisor-weta-digital/)：抽取金屬微粒聚合為三維浮雕與分層歷史敘事的原理。

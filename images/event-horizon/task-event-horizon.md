# event-horizon 主題計畫

## 目標

為 `dynamic-wallpaper` 新增一組受電影 *Event Horizon*（臺灣片名《撕裂地平線》）概念啟發的原創動態桌布主題，資料夾名稱為 `images/event-horizon/`。主題採「空艙壓迫感」：以失聯實驗船、未知重力異象與深空救援作為視覺語彙，不直接重製電影素材。

## Repo 契約

`dwall.sh` 會依目前小時讀取 `images/<style>/<hour>.jpg` 或 `.png`；即使只做 12 張獨特畫面，仍必須提供完整的 `0.jpg` 到 `23.jpg`。

本主題採用：

- 12 張實體 JPG，目標解析度為 `3840x2160`、sRGB
- 12 個相對 symlink 補齊 24 小時檔名
- 不修改 `dwall.sh`、`install.sh` 或 `test.sh`
- 更新 `README.md` 與 `README.zh-tw.md` 的可用樣式清單及預覽表格，預覽使用 `images/event-horizon/12.jpg`
- 新增 `images/event-horizon/README.md`，記錄原創限制、小時敘事、檔案 mapping 與參考連結

## 小時分配

實體 JPG：

- `0.jpg`：遠方冰藍行星旁漂流的無人研究船，深夜、稀疏星光
- `2.jpg`：船體外部與受損通訊桅杆，低光、冷藍金屬
- `4.jpg`：空氣閘與對接環，黎明前的微弱琥珀導引燈
- `6.jpg`：空置維修通道，霧氣、纜線與深長透視
- `8.jpg`：無人的居住艙與觀測窗，晨間偏白的工作照明
- `10.jpg`：工程甲板與工具牆，平靜但不安的藍灰光
- `12.jpg`：中央重力核心室，巨大黑色幾何異象與環形機械結構
- `14.jpg`：控制艙，顯示器只有抽象光形，無可讀文字
- `16.jpg`：反應爐與冷卻管線，午後的琥珀／藍綠對比
- `18.jpg`：紅色緊急照明下的空走廊，無人、無血腥
- `20.jpg`：失穩的核心隔離艙，深黑、微粒與扭曲光線
- `22.jpg`：遠離事故船的無人救援艇與沉寂星空，深夜收束

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

## 美術方向與限制

- 使用原創、寫實的 1990 年代感模組化太空船與工業科幻美術；冷藍、石墨黑、氧化金屬與小面積琥珀／警示紅光為主。
- 場景必須是無人空間：不可出現人物、演員肖像、角色臉孔、太空衣人影、屍體或血腥畫面。
- 不使用電影劇照、片名、logo、台詞、可讀介面文字、可辨識的電影船艦輪廓或直接複製的鏡頭構圖。
- 不生成明顯怪物或 gore；恐怖感由空間尺度、照明、靜止機械與未知重力異象形成。
- 內建 `image_gen` 一次只處理一張主圖；每次產生後先確認本機有本批新圖檔，再裁切／縮放並輸出最終 JPG。若沒有可用本機檔案，停止並先詢問是否改用需 `OPENAI_API_KEY` 的 CLI 流程。

## 參考依據

- 使用者提供的 [IMDb 頁面](https://www.imdb.com/title/tt0119081/)
- 使用者提供的 [中文維基百科條目](https://zh.wikipedia.org/zh-tw/%E9%BB%91%E6%B4%9E%E8%A1%A8%E9%9D%A2)

## 驗證計畫

採非侵入式驗證：

```bash
bash -n dwall.sh install.sh test.sh uninstall.sh
find images/event-horizon -maxdepth 1 \( -type f -o -type l \) -name '*.jpg' | wc -l
find images/event-horizon -maxdepth 1 -type f -name '*.jpg' | wc -l
find images/event-horizon -maxdepth 1 -type l -name '*.jpg' -printf '%f -> %l\n' | sort -V
identify -format '%f %wx%h\n' images/event-horizon/*.jpg | sort -V
./test.sh -h | rg 'event-horizon|Available styles'
git diff --check
```

不要執行 `./test.sh -s event-horizon`，除非明確允許變更目前桌布。

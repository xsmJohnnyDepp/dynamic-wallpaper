# winter-overlook 主題計畫

## 目標

為 `dynamic-wallpaper` 新增一組受電影 *The Shining* 啟發的原創動態桌布主題，暫定資料夾名稱為 `images/winter-overlook/`。主題不直接使用電影劇照、片名 logo、台詞文字、演員肖像或可辨識角色，而是以經典雪中飯店恐怖片的美術語彙做原創 homage。

續集 *Doctor Sleep* 僅作為晚間少量參考，用於破敗回訪、紅光門廊與成年創傷感，不把整組主題改成雙片敘事。

## Repo 契約

`dwall.sh` 會依目前小時讀取 `images/<style>/<hour>.jpg` 或 `.png`，因此即使只做 12-16 張獨特畫面，也仍須提供 `0.jpg` 到 `23.jpg`。

本主題採用：

- 16 張實體 JPG，目標解析度 `3840x2160`
- 8 個 symlink 補齊 24 小時檔名
- 不修改 `dwall.sh`、`install.sh`、`test.sh`
- 更新主 `README.md` 的 available styles / preview 區塊
- 新增 `images/winter-overlook/README.md` 記錄來源與 mapping

## 小時分配

實體 JPG：

- `0.jpg`
- `4.jpg`
- `7.jpg`
- `8.jpg`
- `9.jpg`
- `10.jpg`
- `11.jpg`
- `12.jpg`
- `14.jpg`
- `15.jpg`
- `16.jpg`
- `17.jpg`
- `18.jpg`
- `19.jpg`
- `20.jpg`
- `22.jpg`

Symlink：

- `1.jpg`, `2.jpg`, `3.jpg` -> `0.jpg`
- `5.jpg`, `6.jpg` -> `4.jpg`
- `13.jpg` -> `12.jpg`
- `21.jpg` -> `20.jpg`
- `23.jpg` -> `22.jpg`

## 美術方向

整體重點是「高度還原場景氛圍，不放人物」。不要生成 Jack Nicholson 或任何人物肖像；使用空場景、燈光、鏡面、空椅、吧檯與紅金配色暗示經典酒吧場面。

時段敘事：

- `0-3`: 雪夜遠山飯店外觀，冷藍、孤立、少變化
- `4-6`: 黎明前空走廊，幾何地毯、低視角、一點透視
- `7-12`: 早晨到午後，飯店外觀、大廳、走廊、綠色浴室、Colorado Lounge、Gold Room 空廳
- `14-16`: 雪中迷宮、暴雪車道、紅色電梯/門廊
- `17-20`: 主高潮，Gold Room 靈異酒吧 wide shot、吧檯近景、紅色 restroom 空場景、夜晚 haunted ballroom
- `22-23`: *Doctor Sleep* 式破敗回訪與深夜收束

避免項目：

- 電影劇照或完全照抄原片構圖
- 演員肖像、角色臉、人物剪影
- 可讀的 `REDRUM`、片名 logo、台詞或房號文字
- 完全複製原片地毯圖案
- 血腥、gore、明顯怪物

## 參考依據

- Warner Bros 官方頁：*The Shining* 與 *Doctor Sleep*
- Architectural Digest：David Hicks 幾何地毯設計與 *The Shining* 走廊美術脈絡
- The Guardian：Overlook Hotel 巨大、明亮、空曠室內空間造成恐怖感
- Vanity Fair：*Doctor Sleep* 回到 Kubrick 式 Overlook，但適合作為後段回聲

## 實作結果

- 已完成 16 張實體圖與 8 個相對 symlink，保留 `0.jpg` 到 `23.jpg` 的小時契約。
- 外觀以 Timberline Lodge 的石材、木構、橫向量體與中央煙囪為建築骨架；大型室內以 The Ahwahnee Great Lounge 的尺度、木樑、高窗、陽台與石壁爐為依據。
- 電影場景只轉譯年代美術、色彩、材質與鏡頭語言；沒有把電影劇照作為產圖輸入。
- 使用內建 `image_gen` 一次產生或編修一張，每張都在本機檔案系統確認後才納入 staging。
- 核准的 landscape masters 已後製為 `3840x2160` sRGB JPG；未修改 `dwall.sh`、`install.sh` 或 `test.sh`。

## 驗證計畫

非侵入式驗證：

```bash
bash -n dwall.sh install.sh test.sh uninstall.sh
find images/winter-overlook -maxdepth 1 \( -type f -o -type l \) -name '*.jpg' | wc -l
find images/winter-overlook -maxdepth 1 -type f -name '*.jpg' | wc -l
find images/winter-overlook -maxdepth 1 -type l -name '*.jpg' -printf '%f -> %l\n' | sort -V
identify -format '%f %wx%h\n' images/winter-overlook/*.jpg | sort -V
./test.sh -h | rg 'winter-overlook|Available styles'
git diff --check
```

不要執行 `./test.sh -s winter-overlook`，除非明確允許改變目前桌布。

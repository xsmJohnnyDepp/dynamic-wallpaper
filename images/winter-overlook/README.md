## Source

AI-generated original wallpaper set inspired by the production-design language
of classic snowbound hotel horror. The sequence moves from an isolated mountain
hotel at midnight, through empty daytime interiors, into a storm-darkened gold
ballroom and a decayed late-night return.

The images do not use film stills, actor likenesses, recognizable characters,
logos, dialogue, readable room numbers, or copied set and carpet designs. No
blood or gore.

The exterior massing is grounded in the stone, timber, roof, and central-chimney
details documented by the official [Timberline Lodge art tour][timberline]. The
large public interiors use the scale, exposed beams, tall windows, balconies,
and stone fireplace documented for [The Ahwahnee Great Lounge][ahwahnee]. Film
production-design cues were described textually; film stills were not used as
image inputs.

The shipped masters are still empty rooms. The character brief below is the
next pass: some hours gain one original adult woman, and the wide establishing
views stay empty. `task-shining.md` records the earlier empty-scene plan.

### Hourly sequence (current masters)

16 physical `3840x2160` JPG files and 8 relative symlinks:

| Hours | Image | Scene |
|---|---|---|
| `0-3` | `0.jpg` | Isolated hotel exterior at midnight |
| `4-6` | `4.jpg` | Empty corridor before dawn |
| `7` | `7.jpg` | Hotel exterior at winter dawn |
| `8` | `8.jpg` | Grand lobby in early morning light |
| `9` | `9.jpg` | Sunlit guest-floor corridor |
| `10` | `10.jpg` | Empty green-tiled bathroom |
| `11` | `11.jpg` | Mountain-view lounge |
| `12-13` | `12.jpg` | Empty gold-toned ballroom at noon |
| `14` | `14.jpg` | Snow-covered hedge maze |
| `15` | `15.jpg` | Hotel driveway during a blizzard |
| `16` | `16.jpg` | Red-toned elevator lobby |
| `17` | `17.jpg` | Haunted ballroom and bar at dusk |
| `18` | `18.jpg` | Empty bar counter close-up |
| `19` | `19.jpg` | Red art-deco restroom |
| `20-21` | `20.jpg` | Haunted ballroom at night |
| `22-23` | `22.jpg` | Decayed hotel and red-lit entrance |

### Symlink mapping (current)

- `1.jpg`, `2.jpg`, `3.jpg` -> `0.jpg`
- `6.jpg` -> `4.jpg`
- `13.jpg` -> `12.jpg`
- `21.jpg` -> `20.jpg`
- `23.jpg` -> `22.jpg`

Figure hours below become their own files. Empty hours may stay linked.
If `20` gains a figure, `21` must keep an empty night ballroom of its own
instead of following `20`.

### Creative references

- *The Shining*: snowbound hotel isolation and expansive empty interiors
- *Doctor Sleep*: the late-night decayed return and restrained red light
- David Hicks-inspired geometric design, reinterpreted as original patterns

[timberline]: https://timberlinelodge.com/things-to-do/art-tour/exterior-front-of-the-lodge/
[ahwahnee]: https://www.nps.gov/media/video/view.htm?id=4D0B8098-B9FF-49F7-9806-A4EF2C9F2F83

---

# 人物造型與產圖 brief（日後必讀）

這組的風景是**雪中山間飯店**：石木外觀、長走廊、木樑大廳、綠磚浴室、金廳、紅電梯門、雪樹籬、紅門。人物線搬的是京都／宇治／液態幾何聖殿的**絲襪連褲襪美腿**，不是那三組的衣服，也不是電影角色。

她是原創成年女性。一小時一個，可換臉、髮、妝、衣服色。鎖死的是短裾、連褲襪從腰到趾都是一層膜、以及「人是實的」。不仿可辨識藝人。不畫小孩。不畫血。

24 小時仍要有 `0.jpg`–`23.jpg`。**不是每小時都有人。** 飯店全貌、一點透視長廊、暴雪車道、空的金廳全景繼續空著。空本身是另一個角色。放得下近人的小時才加人，而且要重做前景：頭在門框、拱、椅背或樹籬下面，腳在地毯、磁磚、舞池或雪上。不要把人縮進現有全景的中間。

試作放 `images/winter-overlook/_trials/`（本機；已被忽略，不要提交）。覆寫正式檔前先備份。褲襪商品參考在 `images/neon-dystopia/_trials/`：`pp-10d-beige-side-a.jpg`、`16-C-drysheer.jpg`（乾透 C，不要油亮 B）。

## 鬼

人是實的，站得住、坐得住，邊緣清楚。透的是襪，不是把身體畫成霧。

每一張有人的圖只留**一種**看得懂的鬼證據：

| 證據 | 看得見的成功 | 用在 |
|---|---|---|
| 鏡子是空的 | 她人在房裡；玻璃裡是燈、窗、空椅、浴缸，沒有她的背 | 已經有大鏡子的小時 |
| 雪是平的 | 鞋或腳周圍的雪沒有走到她這裡的腳印 | 雪地 |
| 影子是缺的 | 燈照得到她身後的牆或地板，那裡沒有她的影子 | 沒有鏡子、也沒有雪的室內 |
| 反光地板是空的 | 拋光地面映出燈和窗，沒有她的腿 | 金廳近景 |

不要一槍裡同時催兩種。不要長白壽衣、不要整個人飄起來、不要全身半透明、不要濕亮皮、不要浴缸裡的人、不要兩個小孩、不要可讀的字。

## 不可拆的人物語法

### 剪裁

- 預設：**兩件式短上衣＋短裾**。胸前或背後鑽空可留，當錯開項。
- 布料色跟場景錯開，不要 24 小時同一套骨白裙。可用骨白、黑、暗金、乾玫瑰。金和紅優先留給襪膜和房間，不要衣服、房間、襪三種同時燒成同一個顏色。
- 相鄰有人的小時至少錯開：衣服色、剪裁、髮、妝、姿勢、視線、襪色、腳上有沒有鞋。
- 背面小時頭髮束起或撥到遠側肩，否則臀下弧會被頭髮蓋住。

### 絲襪連褲襪是主體

腿必須在 16:9 裡讀得清楚：人拉近、腿走畫面長邊或佔前景。

**顏色和材質按這一小時的人和場景換。** 不要 24 小時鎖同一雙。偏好是**透膚、全透明**：膜可以染色，皮膚、膝、腿型、趾腹都要從膜裡讀出來。

| 選擇 | 看得見的成功 | 不要畫成 |
|---|---|---|
| 膚色全透 | 對上**同一張**已露出的上臂或腰；一層乾尼龍；瞇眼像裸腿 | 米色塗層、灰膜 |
| 配這一廳的全透 | 膜的顏色對上**這一張裡已經有的**光或材質（壁燈琥珀、窗外雪光、綠磚、紅門、吧台暖金、雪徑冷灰藍、夜的透黑）；皮膚和膝仍透出來 | 實心色褲、不透塗層、乳膠 |
| 透膚黑 | 還看得到皮膚與腿型；鞋口或趾頭仍能證明膜蓋到腳 | 實心黑褲 |

證人：

- 穿鞋：鞋口有襪緣進去，膝後有皺。
- 脫鞋：同一層膜連續蓋過趾腹和趾縫；趾頭是膜裡的趾頭。
- 膚色槍用「腿對上腰／臂」。場景色用「膜對上這一廳的燈或牆，同時皮膚還在」。

從下襬到趾頭是同一層膜。不要局部上色，不要在腳踝停住變成船型襪，不要腳尖一段變裸膚。

**不透明褲襠非必要。** 正面走來、封閉下襬時，不必為了露出褲襠去催開衩。錯的 T 縫（直線劃過股底）不如不畫。

禁：乳膠、濕油亮面、小腿後中縫、實心象牙色褲。

### 膚色

淺、瓷白到淺東亞膚。臉、頸、手臂、腰同一套。上半身偏深、露出的腰／臂偏白是另外兩組反覆修過的錯。腿跟不跟膚色走，看該小時的襪：膚色全透才對上腰／臂；染色全透可以跟膚不同，但皮膚仍要從膜裡透出來。

### 構圖

人不能當一根豎線插在飯店明信片中間。成功的是：

- 側坐椅緣、台階、吧凳（一腿伸、一腿收，腿走長邊）
- 四分之三背面走遠（臀線才入鏡）
- 朝鏡頭走來（腿是主體，但**看不到臀下弧**；腳若朝向鏡頭，趾頭才入鏡）

全組只有 `20` 看鏡頭。其餘看門、雪、紅門、空杯、樹籬、鏡子裡的房間。

鏡頭近一檔。兩側留低細節給桌面圖示，人必須夠大。金廳與夜景不要把人和地面壓進黑裡。

### 腳：襪趾可以入鏡，鞋子依場景

腳永遠在連褲襪裡。可換的是**這一小時有沒有鞋**。

脫鞋時呈現的是襪趾：膜蓋住趾腹，趾縫透得出來，腳掌貼在地毯、磁磚、踏腳或石階上。趾頭入鏡是因為腳本來就朝向鏡頭，或沿地面伸出去而看見趾尖側面。不要把腳掌翻起來對鏡頭。宇治 `19` 正側硬轉腳掌會畫成斷踝。

兩種脫鞋：

- **鞋留在旁邊**：她在這張椅子、這張吧凳上脫下來。空鞋在椅腳或凳下，款式跟本組的晚鞋同一族。
- **房裡沒有鞋**：走廊盡頭、浴室門口、朝鏡頭走來、雪階。不要在腳邊多畫一雙鞋。

穿鞋時，鞋口在腳背上方，襪緣從鞋口進去。這組的鞋是飯店晚鞋，不是宇治的通勤泵，也不是雪靴：

| 場景 | 鞋 | 看得見的結果 |
|---|---|---|
| 金廳、吧台、紅廳 | 暗緞或暗皮，矮彎跟 | 跟明顯矮於細尖高跟；鞋口吞進襪緣 |
| 走廊、大廳、電梯 | 同一高度的暗皮矮跟 | 鞋口乾淨，膜從鞋口進去 |
| 雪地若仍穿鞋 | 仍是這雙晚鞋 | 實用雪靴會把襪緣蓋住，不要 |

繞踝帶只留給一個小時，而且不要跟下襬改在同一槍。開口鞋若只露出裸趾，等於沒穿襪，不要。

### 姿勢決定看不看得見

| 目標 | 鏡頭 |
|---|---|
| 臀下弧 | 站立、四分之三背面 |
| 襪的透明度、染色 | 腿要大。膚色對上同一張的腰或上臂；場景色對上這一廳的燈或牆 |
| 襪趾 | 腳朝向鏡頭，或側向伸出時露出趾尖。腳掌留在地面 |
| 鞋口襪緣 | 腳伸進畫面、鞋還穿著 |
| 側坐 | 看不到臀線 |
| 正面走來 | 看不到背與臀下弧 |

## 產圖提示：身體界線

模型會把 `short` / `mini` / `ghost` / `barefoot` / 單獨的 `5 denier` 映射成安全預設：長白裙、不透色褲、或真的裸腳。

每次生成只改**一個**可見度量。先寫參考圖哪裡不對，再寫新的可見結果。有上限也要有露出下限。

```
ONE CHANGE: [delta].
The current [feature] [wrong landmark].
The new [feature] [success landmark].
Still [ceiling so it does not overshoot].
```

| 不要寫 | 要寫 |
|---|---|
| `mini` / `short skirt` | 正面：下襬在大腿中段，髖骨上半仍蓋住。背面：下襬露出臀部下弧，布仍蓋住臀部上半 |
| `sheer` / `5 denier` 單獨寫 | 膜的顏色對上這一廳的哪盞燈或哪面牆；皮膚、膝、趾腹仍透出來；膝後有皺 |
| `barefoot` | 膜連續蓋過趾腹與趾縫；腳掌貼地。要嘛空鞋在椅邊，要嘛畫面裡沒有鞋 |
| `ghost` / `transparent woman` | 人是實的。透的是襪。另寫這小時的那一種鬼證據 |
| 只有 `still covering` | 那是天花板；還要寫露出下限 |

## 小時地圖

現況都是空景底板。有人的小時從零重做近景，不要拿遠景空景當構圖鎖。

| 小時 | 場景與姿勢 | 下襬 | 襪（全透，配這一景） | 腳 | 鬼的證據 | 現況 |
|---|---|---|---|---|---|---|
| `0`–`3` | 雪夜飯店全貌。留空 | — | — | — | 窗亮著，車道沒有新腳印 | **沿用** `0.jpg`。窗亮；車道是舊雪凹凸，沒有走到門口的新腳印。`1`–`3` symlink |
| `4` | 黎明前長走廊。留空 | — | — | — | 一點透視本身 | **沿用** `4.jpg`。無人。`6` 仍連這張。`5` 已是獨立檔 |
| `5` | 同走廊改近。背四分之三站在打開的門裡，看走廊盡頭。一隻手掌貼門框，約在肩膀高 | 暖棕布只蓋住臀部上半；臀部下弧在膚色膜裡 | 膚色全透，和下背同一調，大腿與膝蓋透出 | **穿鞋**。矮跟偏棕。趾頭不對鏡頭 | 壁燈在身側的走廊牆上 | **正式** `5.jpg`＝`_trials/5-skinfilm-6.jpg` 放大。獨立 3840×2160。`6` 仍連 `4` |
| `6` | 留空，仍連 `4` | — | — | — | — | symlink→`4` |
| `7` | 冬晨外觀。留空 | — | — | — | — | `7.jpg` |
| `8` | 大廳靠窗。側坐扶手椅，一腿沿地毯伸出；看窗外的雪 | 坐下後下襬騎到大腿上段 | 窗外雪光的冷藍，皮膚透出 | **穿鞋**。暗皮矮跟。看見鞋口襪緣，不把腳掌翻向鏡頭 | 大門玻璃裡是雪和空廳，沒有她 | **正式** `8.jpg`＝`_trials/8-v32.jpg` 放大。獨立 3840×2160。兩腿同一層膜 |
| `9` | 日光照進的客房走廊。留空 | — | — | — | — | `9.jpg` |
| `10` | 綠磚浴室。站在門框裡朝內看，浴缸保持空。腿在門框前景 | 大腿中段；髖仍蓋住 | 綠磚的薄綠，腿型仍在 | **脫鞋，房裡沒有鞋**。磁磚上看得見趾尖側面；膜蓋住趾腹；腳掌貼地 | 洗手台上方的鏡子裡是窗、浴缸、洗手台，沒有她 | 空景 `10.jpg` |
| `11` | 山景休息室。留空 | — | — | — | — | `11.jpg` |
| `12` | 正午金廳全景。留空 | — | — | — | 廳是為沒來的宴會佈置的 | `12.jpg` |
| `13` | 同金廳改近。背四分之三沿舞池邊走，看吧台。髮束起 | 露出臀部下弧；布仍蓋住臀部上半 | 壁燈金透，膜一路貼到臀下弧，皮膚仍透出 | **穿鞋**。暗緞矮彎跟 | 拋光地板映出燈，沒有她的腿 | symlink→`12`，將拆 |
| `14` | 雪樹籬死路。人拉近到兩籬之間。背四分之三走向堵住的籬 | 露出臀部下弧；布仍蓋住臀部上半 | 雪徑冷灰藍，皮膚透出 | **穿鞋**。仍是晚鞋，不是雪靴 | 鞋周圍的雪是平的 | 空景 `14.jpg`，將拉近 |
| `15` | 暴風雪車道。留空 | — | — | — | — | `15.jpg` |
| `16` | 兩扇紅電梯門。坐左側紅椅，一腿伸向另一張空椅；看緊閉的紅門 | 下襬騎到大腿上段 | 紅門的薄紅，膝與膚色仍可讀 | **脫鞋，空鞋在椅腳**。伸出的那隻腳沿地毯，趾尖側面入鏡；腳掌貼地；膜蓋住趾腹 | 紅門門面映出對面的空椅，沒有她 | 空景 `16.jpg` |
| `17` | 黃昏金廳全景。留空。空椅子就是其他的鬼 | — | — | — | — | `17.jpg` |
| `18` | 吧台。側坐紅凳，一腿沿踏腳伸向燈；看那杯空酒 | 下襬在大腿上段；膝後有皺 | 吧台灯的暖金，皮膚透出 | **脫鞋，空鞋在凳下**。踏腳上的那隻腳朝燈，襪趾入鏡；膜蓋過趾腹與趾縫；腳掌不翻起 | 背後鏡子裡是燈、窗、酒瓶和空凳，沒有她 | 空景 `18.jpg`。這張先做 |
| `19` | 紅色化妝室。側立在洗手台前，看鏡中的房間 | 大腿中段；髖仍蓋住 | 與 `16` 錯開：煙黑全透，紅光只浮在膜表面，皮膚仍透出 | **穿鞋**。暗皮矮跟，鞋口有襪緣 | 鏡子裡沒有她 | 空景 `19.jpg` |
| `20` | 夜金廳。朝鏡頭走在舞池邊緣。全組只有這張看鏡頭 | 大腿中段；髖仍蓋住 | 夜的透膚黑，看得到皮膚 | **脫鞋，畫面裡沒有鞋**。腳朝鏡頭，趾腹與趾縫從黑膜裡可數 | 拋光地板映出燈和窗，沒有她的腿 | 空景 `20.jpg`，將重做 |
| `21` | 夜金廳再空回來 | — | — | — | — | 不要再 symlink 到有人的 `20`；另存空景 |
| `22` | 破敗飯店與紅門全貌。留空 | — | — | — | 紅光停在台階上 | `22.jpg` |
| `23` | 紅門台階近景。側坐石階，一腿沿台階；看紅門 | 下襬騎到大腿上段 | 雪夜冷藍全透；紅光停在石階，不把小腿染成實心紅 | **脫鞋，畫面裡沒有鞋**。腳掌貼在石階上，趾尖沿台階入鏡；膜蓋住趾腹 | 腳邊的雪是平的 | symlink→`22`，將拆 |

衣服色跟上表錯開即可，第一槍用文字寫，不要鎖死成同一套晚禮服。`18` 用黑衣配暖金襪，`20` 用暗金衣配透膚黑襪，避免衣服和襪同時吃掉房間的金。

## 已驗證流程（沿用宇治／京都／聖殿）

1. 覆寫前先備份：`cp --update=none N.jpg _trials/N-before-character.jpg`（symlink 先拆成獨立檔再備份）。
2. 從零產 `16:9`。第一槍可以場景加人一起出。用文字寫飯店材質。不要拿舊的遠景空景當構圖鎖。
3. 一次一個可見度量。下襬、襪色、脫鞋拆開改。整層襪膜要從下襬連續到趾頭；需要時緊裁腿再羽化貼回，不要局部染色。
4. 寫入：

```bash
convert "$SRC" -filter Lanczos -resize '3840x2160^' -gravity center \
  -extent 3840x2160 -colorspace sRGB -quality 92 \
  "$DEST/_trials/${trial}.jpg"
cp "$DEST/_trials/${trial}.jpg" "$DEST/${hour}.jpg"
```

5. `identify` 確認 `3840×2160` sRGB。未接受的槍只留 `_trials/`。
6. 不要跑會改桌布的 `./test.sh -s winter-overlook`，除非明確要求。

## 失敗模式

- 寫 `ghost`：變長白裙或全身淡出。人要實，透的是襪。
- 寫 `barefoot`：變裸趾。要寫膜蓋過趾腹。
- 側坐硬把腳掌轉正：斷踝。趾頭只在腳本來就朝向鏡頭時入鏡。
- 雪地寫靴子：襪緣消失。雪地要么晚鞋，要么沒有鞋。
- 遠景硬加人：人變小點。重做有地面的近景。
- 綠浴室寫進浴缸：會貼上那部電影。人站在門框裡，浴缸是空的。
- 場景色襪畫成不透色褲：皮膚和膝要還在膜裡。
- 用上一張的人當下一張的姿勢參考：臉和朝向會一起帶過來。

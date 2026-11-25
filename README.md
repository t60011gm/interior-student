# interior-student

北歐風小客廳 3D 互動網站。模型在 Blender 建立，網頁用 three.js 呈現。

## 資料夾

| 路徑 | 內容 |
| --- | --- |
| `nordic_living_room/nordic_living_room.blend` | Blender 原始檔 |
| `nordic_living_room/nordic_living_room.glb` | 從 Blender 匯出的模型 |
| `nordic_living_room/web/` | 互動網頁（`index.html` + 模型），整個資料夾可直接放到靜態網站空間 |

## 本機預覽

網頁需要透過伺服器開啟（直接雙擊 `index.html` 會讀不到模型）：

```bash
python -m http.server 8765 --directory nordic_living_room/web
```

然後打開 http://localhost:8765

## 更新模型

1. 在 Blender 修改 `nordic_living_room.blend`
2. 匯出 glTF Binary（.glb）到 `nordic_living_room/`
3. 把新的 `.glb` 複製到 `nordic_living_room/web/` 覆蓋舊檔

## 網頁功能

- 拖曳旋轉、滾輪縮放
- 點家具看介紹，沙發與扶手椅可換布色
- 點牆面（或清單中的「牆面」）可換壁紙顏色
- 清單中的「天花板」會把鏡頭移進房間往上看，可換天花板顏色（從外面俯瞰時天花板是透明的）
- 白天 / 夜晚切換，落地燈與吊燈可個別開關
- 家具介紹文字與布色在 `index.html` 的 `ITEMS`、`FABRICS` 修改

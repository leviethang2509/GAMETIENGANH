# 🌾 WordFarm — Game Luyện Từ Vựng Tiếng Anh

Game giáo dục theo phong cách **Farmville**, kết hợp luyện tập **từ vựng & ngữ pháp tiếng Anh** thông qua các hoạt động nông trại thú vị.

## ⚡ Quick Start

### 🚀 WordFarmV2 (Current Version — No npm Needed!)

**Double-click to play:**
```
WordFarmV2/RUN.bat
```

✅ **No setup required**  
✅ **No npm, no dependencies**  
✅ **Single HTML file**  
✅ **Works on any browser**

👉 [Full Guide: WordFarmV2/README.md](WordFarmV2/README.md)

---

## 🎮 Gameplay

### Các Chế Độ Quiz

1. **🌱 Gieo Hạt (Planting)** — Trắc nghiệm từ vựng
   - Chọn đáp án đúng để gieo hạt thành công
   - Tiêu tốn: 10 năng lượng
   - Thưởng: 15 EXP

2. **💧 Tưới Nước (Nurturing)** — Điền từ ngữ pháp
   - Hoàn thành câu với động từ/từ đúng
   - Tiêu tốn: 10 năng lượng
   - Thưởng: 20 EXP

3. **🐛 Diệt Sâu (Pest Control)** — Gõ nhanh từ vựng
   - Gõ từ tiếng Anh trong 10 giây
   - Tiêu tốn: 10 năng lượng
   - Thưởng: 25 EXP + 15 vàng

4. **🚜 Thu Hoạch (Harvesting)** — Sắp xếp câu
   - Sắp xếp các từ thành câu đúng
   - Tiêu tốn: 10 năng lượng
   - Thưởng: 40 EXP + vàng (tùy loại cây)

5. **👨‍🌾 Thăm Hàng Xóm Bob**
   - 💧 **Tưới Hộ**: Điền từ → +15 vàng, +20 EXP
   - 🖐️ **Hái Trộm**: Tìm lỗi sai ngữ pháp → +30-40 vàng, +35 EXP
   - ⚠️ Thất bại hái trộm → -12 vàng

### Hệ Thống Cây Trồng

| Cây | Emoji | Giá Bán | Yêu Cầu | Thời Gian Lớn |
|-----|-------|---------|---------|--------------|
| Lúa mạch | 🌾 | 30 | Lv.1 | 40s |
| Ngô | 🌽 | 35 | Lv.1 | 50s |
| Cà rốt | 🥕 | 25 | Lv.2 | 35s |
| Cà chua | 🍅 | 40 | Lv.3 | 55s |
| Táo | 🍎 | 50 | Lv.4 | 70s |
| Quả dâu | 🫐 | 45 | Lv.3 | 60s |
| Bí ngô | 🎃 | 60 | Lv.4 | 80s |

### Vật Phẩm Hỗ Trợ

| Vật Phẩm | Giá | Hiệu Ứng |
|----------|-----|---------|
| 🔎 Kính Lúp | 30 vàng | Gợi ý câu hỏi |
| 📖 Sách Phép | 50 vàng | Giải hộ 1 câu (thành công) |
| 🌿 Phân Bón | 25 vàng | Tăng tốc độ lớn cây (×2) |

## 🚀 Cách Chạy Game

### Phương Pháp 1: Mở File Trực Tiếp
```bash
# Vào thư mục
cd WordFarm

# Mở file index.html bằng browser yêu thích
# Windows:
start index.html

# macOS:
open index.html

# Linux:
xdg-open index.html
```

### Phương Pháp 2: Dùng Python HTTP Server
```bash
cd WordFarm
python -m http.server 8000
# Sau đó vào http://localhost:8000 trên browser
```

### Phương Pháp 3: Dùng Node.js
```bash
cd WordFarm
npx http-server
# Mở http://localhost:8080
```

### Phương Pháp 4: VS Code Live Server
- Cài extension **Live Server** cho VS Code
- Right-click trên `index.html` → chọn "Open with Live Server"
- Browser sẽ tự động mở ở `http://localhost:5500`

## 🎨 Cấu Trúc Thư Mục

```
WordFarm/
├── index.html                 # Entry point chính
├── js/
│   ├── app.js                # Main app logic
│   ├── data/
│   │   ├── config.js         # Metadata cây trồng, shop
│   │   └── questions.js      # Ngân hàng câu hỏi (60+ câu)
│   ├── systems/
│   │   ├── saveSystem.js     # Lưu/tải game qua LocalStorage
│   │   ├── audioSystem.js    # Âm thanh Web Audio API
│   │   └── cropSystem.js     # Quản lý vòng đời cây trồng
│   ├── ui/
│   │   ├── hud.js            # HUD thống kê + GSAP animations
│   │   ├── quiz.js           # Modal quiz (4 loại)
│   │   ├── shop.js           # Giao diện cửa hàng
│   │   └── neighbor.js       # Giao diện thăm láng giềng
│   └── scenes/
│       └── FarmGrid.js       # Render lưới nông trại 8 ô
└── assets/
    └── audio/                # (Chưa dùng — dùng Web Audio API)
```

## 📊 Hệ Thống Tiến Trình

### Leveling System
- **Cách tính EXP**: Mỗi câu trả lời đúng → +15 đến +40 EXP
- **Lên cấp**: Khi tích lũy đủ EXP (Level × 100)
- **Lợi ích**: Mở khóa cây trồng mới, vật phẩm shop

### Năng Lượng (Energy)
- **Max**: 100 năng lượng
- **Tiêu tốn**: 10 năng lượng/câu hỏi
- **Hồi phục**: 1 năng lượng/3 giây

### Tiền Tệ (Vàng)
- **Kiếm từ**: Thu hoạch cây, diệt sâu, hái hàng xóm
- **Dùng cho**: Mua hạt giống, vật phẩm hỗ trợ

## 💾 Lưu Trữ Dữ Liệu

Game dùng **LocalStorage** browser để lưu tiến độ:
- Được mã hóa nhẹ bằng `btoa()` (Base64)
- Tự động lưu mỗi 3 giây (mỗi tick game)
- Tự động lưu khi thoát tab/browser

### Xóa Save Game
Mở DevTools (F12) → Console → gõ:
```javascript
DevTools.reset()  // Reset game hoàn toàn
```

## 🛠️ Tính Năng Phát Triển

### Công Nghệ Dùng
- **Vanilla JavaScript** — Không framework nặng
- **LocalStorage** — Lưu trữ nhẹ, không cần server
- **Web Audio API** — Âm thanh tổng hợp (không file MP3)
- **GSAP** — Animations mượt (CDN fallback CSS)
- **CSS3** — Responsive design

### DevTools (Debug Mode)
Mở Console (F12) và chạy:
```javascript
DevTools.levelUp()           // Lên cấp ngay
DevTools.addGold(100)        // Thêm 100 vàng
DevTools.dumpState()         // Xem state game
DevTools.reset()             // Reset hoàn toàn
```

## 🎓 Nội Dung Học Tập

### Từ Vựng
- 15+ từ vựng nông trại cơ bản
- Tên cây trồng, công cụ, hành động
- Từ có liên quan đến nông nghiệp

### Ngữ Pháp
- Thì Hiện Tại Tiếp Diễn (Present Continuous)
- Thì Quá Khứ Đơn (Past Simple)
- Thì Hoàn Thành (Present Perfect)
- Câu Điều Kiện Loại 2 (Conditional Type 2)
- Động từ Khuyết Thiếu (Modal Verbs)

### Phong Cách Học
- **Gamification**: Điểm, cấp độ, thành tựu
- **Spaced Repetition**: Câu hỏi ngẫu nhiên từ ngân hàng
- **Context-Based**: Học từ/ngữ pháp qua bối cảnh nông trại
- **Immediate Feedback**: Phản hồi tức thì với âm thanh & animation

## 🔧 Mở Rộng Game

### Thêm Câu Hỏi Mới
1. Mở file `WordFarm/js/data/questions.js`
2. Thêm object vào mảng tương ứng (ví dụ `DB.planting`)
3. Save file — game sẽ tự load câu mới

**Ví dụ:**
```javascript
DB.planting.push({
  id: 16,
  q: "Từ nào có nghĩa là 'Cánh đồng'?",
  opts: ["Forest", "Field", "Mountain", "Lake"],
  ans: "Field"
});
```

### Thêm Cây Trồng Mới
1. Thêm metadata vào `CROP_META` trong `config.js`
2. Thêm hạt giống vào `SHOP_SEEDS`
3. Cập nhật `SaveSystem.DEFAULT_STATE.inventory`

### Tùy Chỉnh Giao Diện
- Tất cả CSS nằm trong `<style>` của `index.html`
- Thay đổi màu sắc, font, kích thước ở đó
- Responsive design — tự động fit mobile, tablet, desktop

## 🐛 Troubleshooting

### Game không load
- Kiểm tra console (F12) xem có error không
- Đảm bảo tất cả file `.js` được tải từ đúng đường dẫn
- Thử clear browser cache (Ctrl+Shift+Delete)

### Âm thanh không phát
- Web Audio API cần user gesture trước (click vào game)
- Một số browser require HTTPS để Audio hoạt động
- Kiểm tra volume & speaker hệ thống

### Save game không lưu
- LocalStorage có hạn ~5-10MB (đủ cho game này)
- Nếu dùng Private/Incognito mode, LocalStorage sẽ xóa khi đóng
- Kiểm tra quyền truy cập LocalStorage trong DevTools

## 📝 License

Miễn phí dùng & phát triển. Đây là project học tập.

## 🎯 Mục Tiêu Học Tập

Qua game này, người chơi sẽ:
- ✅ Học 50+ từ vựng nông trại tiếng Anh
- ✅ Luyện 6 chủ đề ngữ pháp quan trọng
- ✅ Phát triển phản xạ & phát âm (gõ nhanh)
- ✅ Hiểu context trong thực tế
- ✅ Tạo thói quen học tập thường xuyên (gamification)

---

**Happy Farming & Happy Learning! 🌾📚**

Có câu hỏi? Mở file `js/app.js` và xem DevTools console commands.

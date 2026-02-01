# 📱 Hướng Dẫn Build APK - Smart AutoClicker Vietnamese

## 🚀 Cách 1: GitHub Actions (KHUYẾN NGHỊ - Nhanh nhất)

**Không cần cài gì cả! Build trên cloud GitHub.**

### Bước 1: Push workflow lên GitHub
```bash
cd c:\Users\Administrator\Desktop\Smart-AutoClicker
git add .github/workflows/build-apk.yml
git commit -m "ci: Add GitHub Actions workflow for APK build"
git push origin master
```

### Bước 2: Kích hoạt build
1. Mở: https://github.com/nguyenhoaithuongabc1-create/Smart-AutoClicker-Vietnamese
2. Click tab **Actions**
3. Click workflow **"Build Android APK"**
4. Click nút **"Run workflow"** → **"Run workflow"**
5. Đợi ~5-10 phút

### Bước 3: Download APK
1. Sau khi build xong, click vào workflow run
2. Scroll xuống phần **Artifacts**
3. Download file `smart-autoclicker-vietnamese-debug`
4. Giải nén và cài APK lên Android

**✅ Hoàn thành! APK của bạn sẵn sàng.**

---

## 💻 Cách 2: Build Local (Cần cài đặt)

### Yêu Cầu:
- ❌ **Hiện tại KHÔNG THỂ** vì thiếu JDK
- Bạn chỉ có JRE 8 32-bit
- Cần: **JDK 17 hoặc 21** (64-bit khuyến nghị)

### Cài Đặt JDK:
1. Download JDK 17: https://adoptium.net/temurin/releases/
2. Chọn:
   - Version: **17**
   - Operating System: **Windows**
   - Architecture: **x64** (nếu có 64-bit Windows)
   - Package Type: **JDK**
3. Cài đặt và set `JAVA_HOME`

### Build Command:
```bash
cd c:\Users\Administrator\Desktop\Smart-AutoClicker
.\gradlew.bat assembleDebug
```

APK sẽ ở: `smartautoclicker\build\outputs\apk\debug\`

**⚠️ Lưu ý:** Windows 32-bit có thể gặp vấn đề memory. Xem `build-requirements.md`

---

## ☁️ Cách 3: Online Build Service

### AppVeyor / CircleCI
- Free cho open source
- Tương tự GitHub Actions
- Cần config

---

## 📊 So Sánh

| Phương pháp | Thời gian | Độ khó | Yêu cầu |
|-------------|-----------|--------|---------|
| **GitHub Actions** | ~5-10 phút | ⭐ Dễ | Chỉ cần GitHub account |
| **Local Build** | ~3-5 phút | ⭐⭐⭐ Khó | JDK 17+, Android SDK |
| **Online Service** | ~5-10 phút | ⭐⭐ Trung bình | Account service |

---

## 🎯 Khuyến Nghị

**👉 Dùng GitHub Actions** - Đơn giản, nhanh, không cần cài gì!

Chỉ cần:
```bash
git add .github/workflows/build-apk.yml BUILD_GUIDE.md
git commit -m "docs: Add build guide and CI workflow"
git push
```

Sau đó vào GitHub Actions và run workflow!

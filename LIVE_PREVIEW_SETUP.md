# 🔴 Live Website Preview Setup Guide

## ✅ Setup Complete!

Automated website live preview system telah berhasil diimplementasikan untuk **tams.codes**.

---

## 📁 Files Created

### 1. GitHub Actions Workflow
**File:** `.github/workflows/website-stream.yml`
- **Fungsi:** Mengambil screenshot otomatis dari https://tams.codes/
- **Schedule:** Setiap 6 jam (cron: `0 */6 * * *`)
- **Manual Trigger:** Tersedia via `workflow_dispatch`

### 2. Screenshot Storage
**Folder:** `profile-assets/`
- **File:** `website-stream.png` (1280x720 resolution)
- **Update:** Auto-commit oleh GitHub Actions Bot

### 3. README Update
**File:** `README.md`
- **Section Baru:** Live Preview (setelah Snake contribution)
- **Theme:** Cyberpunk purple (#8a2be2, #4b0082)
- **Features:** Clickable link ke tams.codes

---

## 🚀 First Run: Manual Trigger

Untuk menjalankan screenshot pertama kali secara manual:

### Step 1: Buka GitHub Actions
1. Pergi ke: https://github.com/el-pablos/el-pablos/actions
2. Klik workflow **"Website Live Stream"** di sidebar kiri

### Step 2: Manual Trigger
1. Klik tombol **"Run workflow"** (dropdown)
2. Pilih branch: **main**
3. Klik **"Run workflow"** (hijau)

### Step 3: Monitor Progress
1. Tunggu workflow selesai (~1-2 menit)
2. Status akan berubah dari 🟡 (running) → ✅ (success)
3. Screenshot akan otomatis ter-commit ke repository

### Step 4: Verify
1. Refresh halaman profile: https://github.com/el-pablos
2. Screenshot tams.codes akan muncul di section "Live Preview"

---

## ⚙️ Technical Details

### Workflow Configuration
```yaml
Schedule: Every 6 hours (0 */6 * * *)
Screenshot Tool: SjoerdHekking/website-screenshot-action@v1.1
Auto-commit: stefanzweifel/git-auto-commit-action@v4
Resolution: 1280x720
Target URL: https://tams.codes/
```

### Auto-Update Schedule
- **00:00 UTC** - Midnight update
- **06:00 UTC** - Morning update
- **12:00 UTC** - Noon update
- **18:00 UTC** - Evening update

### File Paths
```
Repository: el-pablos/el-pablos
Screenshot: profile-assets/website-stream.png
Workflow: .github/workflows/website-stream.yml
README: README.md (line 81-88)
```

---

## 🔧 Troubleshooting

### Screenshot tidak muncul?
1. Pastikan workflow sudah dijalankan minimal 1x (manual trigger)
2. Cek GitHub Actions logs untuk error
3. Verifikasi file `profile-assets/website-stream.png` ada di repository

### Workflow gagal?
1. Cek permissions: Settings → Actions → General → Workflow permissions
2. Pastikan "Read and write permissions" enabled
3. Re-run workflow dari Actions tab

### Screenshot tidak update?
1. Cek cron schedule sudah berjalan (Actions → Website Live Stream)
2. Verifikasi tidak ada error di workflow logs
3. Manual trigger untuk force update

---

## 📊 Monitoring

### Check Workflow Status
```bash
# Via GitHub CLI (jika installed)
gh workflow view "Website Live Stream"
gh run list --workflow=website-stream.yml
```

### Check Last Update
```bash
# Via Git
git log --all --oneline --grep="CI: Update website live stream"
```

### View Screenshot Locally
```bash
# Clone repository
git clone https://github.com/el-pablos/el-pablos.git
cd el-pablos
open profile-assets/website-stream.png  # macOS
xdg-open profile-assets/website-stream.png  # Linux
```

---

## 🎨 Customization

### Change Update Frequency
Edit `.github/workflows/website-stream.yml`:
```yaml
schedule:
  - cron: '0 */3 * * *'  # Every 3 hours
  - cron: '0 0 * * *'    # Daily at midnight
  - cron: '0 */12 * * *' # Every 12 hours
```

### Change Screenshot Resolution
Edit `.github/workflows/website-stream.yml`:
```yaml
with:
  width: 1920   # Full HD width
  height: 1080  # Full HD height
```

### Change Target Website
Edit `.github/workflows/website-stream.yml`:
```yaml
with:
  url: https://your-website.com/
```

---

## 📝 Commit History

```
be3bf29 - feat: Add automated website live preview with GitHub Actions
534ae44 - fix: Remove excessive indentation in social media badges
f7a521a - ehehe
```

---

## ✨ Features Implemented

✅ Automated screenshot system  
✅ 6-hour update schedule  
✅ Manual trigger support  
✅ Auto-commit to repository  
✅ README integration  
✅ Cyberpunk theme consistency  
✅ Clickable preview link  
✅ Update notification  
✅ Proper indentation (no code block)  
✅ Placeholder screenshot  

---

## 🎯 Next Steps

1. **Manual trigger workflow** untuk screenshot pertama
2. **Verify** screenshot muncul di profile
3. **Monitor** auto-update setiap 6 jam
4. **Customize** jika diperlukan (resolution, frequency, etc.)

---

## 📞 Support

Jika ada masalah:
1. Check GitHub Actions logs
2. Verify workflow permissions
3. Re-run workflow manually
4. Check repository settings

---

**Status:** ✅ **READY TO USE**  
**Last Updated:** 2025-10-14  
**Commit:** be3bf29


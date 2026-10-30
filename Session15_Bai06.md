# Bài 6: Môi trường làm việc số cho dự án Green-Tech

## 1. Cấu trúc thư mục
```
GreenTech_Project/
├── 01_Code_CamBien/     (code cảm biến, chỉ đội Dev)
├── 02_BaoCao/           (báo cáo gốc, đội dự án)
├── 03_NhaDauTu/         (chỉ PDF báo cáo đã duyệt)
└── 04_DoiTac_ThietBi/   (tài liệu cần đối tác góp ý)
```

## 2. Cấu trúc Channel
| Channel | Mục đích | Ai đăng |
|---|---|---|
| `#thong-bao` | Deadline, quyết định chung | Trưởng dự án |
| `#ky-thuat-cam-bien` | Thảo luận lỗi cảm biến (mỗi lỗi một thread) | Đội Dev |
| `#tien-do-task` | Cập nhật Task | Tất cả |
| `#tan-gau` | Chuyện ngoài lề | Tất cả |

## 3. Phân quyền
| Đối tượng | Tài liệu | Quyền | Phạm vi |
|---|---|---|---|
| Đội Dev | `01_Code_CamBien` | Editor | Restricted (Group) |
| Nhà đầu tư | PDF báo cáo | Viewer | Restricted, hết hạn 14 ngày |
| Đối tác thiết bị | `04_DoiTac_ThietBi` | Commenter | Restricted (email đối tác) |

**File `.env`:** không đưa lên Drive chung hay Git (thêm vào `.gitignore`, chỉ commit `.env.example`). Nếu buộc phải lưu thì để Restricted, chỉ người cần dùng, không "Anyone with the link".

## 4. Ba chức năng
- **Lưu trữ (Hybrid):** cài Drive for desktop, đồng bộ `01_Code_CamBien` (Mirror), kiểm tra tick xanh sau Ctrl + S; code quản lý bằng Git.
- **Chia sẻ:** nhà đầu tư Viewer, đối tác Commenter như bảng trên.
- **Giao tiếp:** trong thread lỗi cảm biến, bấm tin nhắn → Create Task, điền người phụ trách và Deadline.

## 5. Bàn giao (Transfer Ownership)
Share → chọn người nhận → đặt Editor → Transfer ownership → người nhận chấp nhận → gỡ quyền người cũ, đổi mật khẩu/key.

## 6. Kiểm thử: lỡ xóa folder `sensors`
1. Báo cả nhóm, ngừng sửa thư mục.
2. Drive web → Trash → chuột phải `sensors` → **Restore**.
3. Nếu đã xóa vĩnh viễn: nhờ quản trị viên Workspace khôi phục trong Admin console.
4. Nếu chỉ mất nội dung file: Manage versions → chọn bản cũ. Code thì lấy lại từ Git.
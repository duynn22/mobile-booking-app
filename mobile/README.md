# Git Workflow cho đồ án Mobile Booking App

Tài liệu này quy định **cách tạo branch, pull, push, merge code** để cả team làm việc **không conflict – không mất code – đúng chuẩn đồ án**.

---

## 1. Quy tắc chung (BẮT BUỘC)

* Nhánh `main`:

  * Chỉ chứa code **ổn định, demo được**
  * ❌ **KHÔNG ai được code trực tiếp trên `main`**

* Mỗi thành viên:

  * Làm việc trên **branch riêng**
  * Tên branch theo mẫu:

    ```
    feature/<ten-chuc-nang>
    ```

Ví dụ:

```
feature/auth
feature/booking
feature/profile
feature/admin
```

---

## 2. Quy trình làm việc HẰNG NGÀY (AI CŨNG PHẢI THEO)

### Bước 1: Luôn pull code mới nhất

```bash
git checkout main
git pull origin main
```

👉 Đảm bảo máy mình không bị thiếu code của người khác.

---

### Bước 2: Tạo branch cho chức năng mình làm

Ví dụ: **làm Login Screen**

```bash
git checkout -b feature/auth
```

👉 Chỉ tạo 1 lần. Các lần sau chỉ cần `git checkout feature/auth`.

---

### Bước 3: Code đúng phạm vi của mình

Ví dụ với Login Screen:

* Chỉ code trong:

  ```
  mobile/lib/screens/auth/
  ```

* Tạo file:

  ```
  login_screen.dart
  ```

❌ Không sửa file của người khác
❌ Không sửa `main.dart`, `app.dart` khi chưa thống nhất

---

### Bước 4: Commit code (NHỎ – RÕ RÀNG)

```bash
git status
git add mobile
git commit -m "feat: add login screen UI"
```

Quy ước commit message:

* `feat:` thêm tính năng
* `fix:` sửa lỗi
* `chore:` việc lặt vặt

---

### Bước 5: Push lên branch của mình (KHÔNG push main)

```bash
git push origin feature/auth
```

---

### Bước 6: Tạo Pull Request (PR) trên GitHub

* Base branch: `main`
* Compare branch: `feature/auth`
* Title: `Add login screen UI`
* Description:

  * Đã làm: Login UI
  * Chưa làm: Gọi API

👉 Leader review xong mới merge.

---

### Bước 7: Sau khi merge xong

```bash
git checkout main
git pull origin main
git branch -d feature/auth
```

---

## 3. Những điều CẤM KỴ 🚨

❌ `git push origin main`
❌ `git push -f`
❌ Code chung 1 file screen
❌ Merge khi chưa pull `main` mới nhất

---

## 4. Sơ đồ dễ nhớ

```
main
  ↑
  | (merge)
feature/auth
feature/booking
feature/profile
```

👉 Code ở feature → merge vào main

---

## 5. Checklist trước khi push

* [ ] Đang ở đúng branch chưa?
* [ ] Đã pull `main` mới nhất chưa?
* [ ] Chỉ add đúng thư mục mình làm chưa?
* [ ] Commit message rõ ràng chưa?

---

## 6. Kết luận

Làm đúng quy trình này sẽ:

* Tránh conflict
* Không mất code
* Repo nhìn chuyên nghiệp
* Dễ demo và dễ chấm điểm

👉 **Mọi thành viên bắt buộc tuân theo tài liệu này.**

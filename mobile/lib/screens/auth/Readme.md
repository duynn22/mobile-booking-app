# Authentication Screens #2

This folder contains all authentication-related screens for the Medical Appointment Booking mobile app.

## 📱 Screens Overview

### Login Screen
**File:** `login_screen.dart`  
**ClickUp Task:** #US-09  
**Description:** User login interface with email/password authentication

**Features:**
- Email and password input fields
- Form validation
- Remember me checkbox
- Forgot password link
- Navigation to registration screen
- JWT token storage after successful login

**Dependencies:**
- Authentication API (`/api/auth/login`)
- Shared preferences for token storage
- Form validation utilities

**Status:** ✅ Completed

---

### Registration Screen
**File:** `register_screen.dart`  
**ClickUp Task:** #US-09  
**Description:** New user registration interface

**Features:**
- Full name input
- Email validation
- Password strength indicator
- Confirm password field
- Terms and conditions acceptance
- Phone number input (optional)
- Role selection (Patient/Doctor)

**Validations:**
- Email format check
- Password minimum 8 characters
- Password must contain: uppercase, lowercase, number, special char
- Passwords must match

**Status:** ✅ Completed

---

## 🔗 Related ClickUp Tasks

### Epic: E2 - Auth & Identity
- **US-08:** Setup Backend Infrastructure - #8x1y2z
- **US-09:** User Authentication - #9a2b3c
- **US-10:** Setup Mobile App Infrastructure - #0d4e5f

### Individual Tasks (US-09 breakdown):
- Setup auth middleware - #8a2x4k ✅
- Code API POST /register với validation - #7b3c5d ✅
- Code API POST /login với JWT - #6c4d7e ✅
- Design login_screen.dart UI - #5e6f8g ✅
- Code registration form validation - #4g7h9i ✅
- Integrate auth APIs với Flutter - #3h8i0j ✅
- Handle JWT token storage - #2i9j1k ✅
- Test auth flow E2E - #1j0k2l 🔄 In Progress

---

## 🚀 How to Use

### Login Screen
```dart
// Navigate to login screen
Navigator.push(
  context,
  MaterialPageRoute(builder: (context) => LoginScreen()),
);
```

### Registration Screen
```dart
// Navigate to registration screen
Navigator.push(
  context,
  MaterialPageRoute(builder: (context) => RegisterScreen()),
);
```

---

## 🧪 Testing

### Unit Tests
Located in: `/test/screens/auth/`

**Coverage:**
- Email validation logic
- Password strength checker
- Form validation rules
- API integration mocks

**Run tests:**
```bash
flutter test test/screens/auth/
```

### E2E Tests
**Scenarios:**
1. Successful login flow
2. Invalid credentials error handling
3. Registration with valid data
4. Registration with duplicate email
5. Password mismatch validation

**Related ClickUp Task:** #1j0k2l

---

## 📝 Code Style

Following Flutter best practices:
- StatefulWidget for forms with state management
- TextEditingController for input fields
- Form validators for validation logic
- async/await for API calls
- Error handling with try-catch
- Loading indicators during API calls

---

## 🔐 Security Considerations

1. **Password Handling:**
   - Never store plain text passwords
   - Hash on backend before storage
   - Use HTTPS for all auth requests

2. **Token Management:**
   - Store JWT in secure storage (flutter_secure_storage)
   - Refresh token mechanism
   - Auto-logout on token expiry

3. **Input Validation:**
   - Client-side validation (UX)
   - Server-side validation (Security)
   - XSS prevention

**Related Security Task:** Part of #9a2b3c

---

## 🐛 Known Issues

None at the moment. All tests passing ✅

**Report bugs:** Create task in ClickUp under Epic E2 with tag `[BUG]`

---

## 📚 Dependencies

```yaml
dependencies:
  flutter:
    sdk: flutter
  http: ^0.13.5          # API calls
  provider: ^6.0.5       # State management
  shared_preferences: ^2.1.0  # Token storage
  flutter_secure_storage: ^8.0.0  # Secure token storage
  email_validator: ^2.1.17  # Email validation
```

---

## 👥 Contributors

- **Trần Quốc Hoàng** - Frontend Lead (login_screen.dart)
- **Ngô Hồng Dũng** - Backend API integration
- **Nguyễn Văn Tân** - Testing & QA

---

## 📅 Development Timeline

| Task | Status | Completed | ClickUp |
|------|--------|-----------|---------|
| Design UI mockups | ✅ Done | Feb 10 | #5e6f8g |
| Implement login screen | ✅ Done | Feb 12 | #5e6f8g |
| Implement register screen | ✅ Done | Feb 13 | #4g7h9i |
| API integration | ✅ Done | Feb 14 | #3h8i0j |
| Write unit tests | ✅ Done | Feb 15 | #1j0k2l |
| E2E testing | 🔄 In Progress | Feb 16 | #1j0k2l |

---

## 🔄 Recent Changes

### Feb 16, 2025 - Improved validation - #4g7h9i
- Added real-time password strength indicator
- Enhanced email format validation
- Fixed keyboard dismiss issue on submit

### Feb 15, 2025 - Security enhancements - #3h8i0j
- Migrated to flutter_secure_storage for token
- Added auto-logout on token expiry
- Implemented refresh token flow

### Feb 14, 2025 - Initial implementation - #5e6f8g
- Created login_screen.dart
- Created register_screen.dart
- Basic form validation

---

## 📖 Documentation

For more details, see:
- [API Documentation](../../docs/api/auth.md)
- [Testing Guide](../../docs/testing/auth_tests.md)
- [ClickUp Sprint Board](https://app.clickup.com/sprint-board)

---

## ⚠️ Important Notes

1. **Environment Variables:**
   - API endpoint must be configured in `.env` file
   - Different endpoints for dev/staging/prod

2. **First Time Setup:**
   ```bash
   flutter pub get
   flutter run
   ```

3. **Debugging:**
   - Use Flutter DevTools for debugging
   - Check console logs for API errors
   - Verify API endpoint is reachable

---

**Last Updated:** February 16, 2025  
**ClickUp Epic:** E2 - Auth & Identity  
**Sprint:** Sprint 1 (Feb 9 - Feb 22)

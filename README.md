# Mobile Booking App

Ứng dụng mobile đặt lịch khám bệnh.

## Tech Stack
- Flutter (Mobile)
- NodeJS + Express (Backend)
- MongoDB

## General rule
1️⃣ Branch rule
- ❌ Không commit trực tiếp vào main
- ✅ Làm việc trên feature/*
- ✅ Merge qua pull request

2️⃣ Cấu trúc repo CHỐT CỨNG
- backend/  → NodeJS + Express
- mobile/   → Flutter
- docs/     → UML, báo cáo

## Structure
- lib/
- ├── main.dart
- ├── app.dart
- ├── routes/
- │   └── app_routes.dart
- ├── screens/
- │   ├── auth/
- │   │   ├── login_screen.dart
- │   │   └── register_screen.dart
- │   ├── home/
- │   │   └── home_screen.dart
- │   ├── booking/
- │   │   ├── booking_screen.dart
- │   │   └── booking_detail_screen.dart
- │   ├── profile/
- │   │   └── profile_screen.dart
- │   └── admin/
- │       └── admin_dashboard.dart
- ├── models/
- ├── services/
- │   ├── api_service.dart
- │   └── auth_service.dart
- └── utils/

## Run Backend
cd backend
npm install
npm start

## Run Mobile
cd mobile
flutter pub get
flutter run



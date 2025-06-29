# Hệ Thống Học Viện - Frontend

Ứng dụng web frontend cho hệ thống quản lý học viện được xây dựng bằng Vue.js 3, TypeScript, và Ant Design Vue.

## 📋 Mục lục

- [Yêu cầu hệ thống](#yêu-cầu-hệ-thống)
- [Cài đặt](#cài-đặt)
- [Cấu trúc dự án](#cấu-trúc-dự-án)
- [Mô tả các module](#mô-tả-các-module)
- [Scripts có sẵn](#scripts-có-sẵn)
- [Công nghệ sử dụng](#công-nghệ-sử-dụng)
- [Cấu hình](#cấu-hình)

## 🔧 Yêu cầu hệ thống

Đảm bảo bạn đã cài đặt các phần mềm sau:

- **Node.js**: >= 18.0.0
- **npm**: >= 8.0.0 hoặc **yarn**: >= 1.22.0
- **Git**: Latest version

### Kiểm tra version hiện tại:

```bash
node --version
npm --version
```

## 🚀 Cài đặt

### 1. Clone repository

```bash
git clone https://github.com/nguyenminh37/front-end-2.git
cd front-end-2
```

### 2. Cài đặt dependencies

```bash
npm install
```

hoặc sử dụng yarn:

```bash
yarn install
```

### 3. Chạy ứng dụng ở môi trường development

```bash
npm run dev
```

Ứng dụng sẽ chạy tại: `http://localhost:5173`

### 4. Build cho production

```bash
npm run build
```

### 5. Preview bản build

```bash
npm run preview
```

## 📁 Cấu trúc dự án

```
frontend/
├── public/                 # Tài nguyên tĩnh
│   └── vite.svg
├── src/
│   ├── assets/            # Tài nguyên (hình ảnh, icons)
│   │   ├── vue.svg
│   │   └── images/
│   ├── routers/           # Cấu hình routing
│   │   └── index.ts
│   ├── services/          # API services và tiện ích
│   │   ├── api.ts         # API endpoints
│   │   ├── callApi.ts     # HTTP client wrapper
│   │   ├── firebaseConfig.tsx # Cấu hình Firebase
│   │   └── uploadImage.tsx # Service upload ảnh
│   ├── stores/            # State management (Pinia)
│   │   ├── expired.ts     # Store quản lý session
│   │   └── user.ts        # Store thông tin user
│   ├── views/             # Components trang
│   │   ├── Layout.vue     # Layout chính
│   │   ├── Login.vue      # Trang đăng nhập
│   │   ├── admin/         # Các trang dành cho admin
│   │   ├── student/       # Các trang dành cho sinh viên
│   │   └── teacher/       # Các trang dành cho giáo viên
│   ├── App.vue            # Component gốc
│   ├── main.ts            # Entry point
│   ├── style.css          # Global styles
│   └── global.d.ts        # Type definitions
├── index.html             # HTML template
├── package.json           # Dependencies và scripts
├── tsconfig.json          # TypeScript configuration
├── vite.config.ts         # Vite configuration
└── README.md
```

## 🧩 Mô tả các module

### 1. **Core Framework**
- **Vue 3** (v3.5.13): Framework JavaScript progressive
- **TypeScript** (v5.7.2): Superset của JavaScript với type checking
- **Vite** (v6.2.0): Build tool nhanh và hiện đại

### 2. **UI Framework & Styling**
- **Ant Design Vue** (v4.2.6): Thư viện UI components
- **@ant-design/icons-vue** (v7.0.1): Bộ icons của Ant Design
- **TailwindCSS** (v4.1.3): Utility-first CSS framework

### 3. **State Management & Routing**
- **Pinia** (v3.0.2): Store pattern cho Vue 3
- **Vue Router** (v4.5.0): Router chính thức cho Vue.js

### 4. **HTTP Client & API**
- **Axios** (v1.9.0): HTTP client cho API calls
- **jwt-decode** (v4.0.0): Thư viện decode JWT tokens

### 5. **Utilities & Helpers**
- **Lodash** (v4.17.21): Utility library
- **Day.js** (v1.11.13): Thư viện xử lý date/time nhẹ
- **Vue3 Toastify** (v0.2.8): Notifications/toast messages

### 6. **Firebase Integration**
- **Firebase** (v11.8.0): Platform backend-as-a-service (Authentication, Storage, etc.)

### 7. **Module Descriptions**

#### **Services Module** (`src/services/`)
- `api.ts`: Định nghĩa các API endpoints và methods
- `callApi.ts`: Wrapper cho Axios với interceptors và error handling
- `firebaseConfig.tsx`: Cấu hình và khởi tạo Firebase services
- `uploadImage.tsx`: Service chuyên biệt cho upload hình ảnh

#### **Stores Module** (`src/stores/`)
- `user.ts`: Quản lý state thông tin người dùng (profile, authentication)
- `expired.ts`: Quản lý session expiration và auto-logout

#### **Views Module** (`src/views/`)
- `Layout.vue`: Layout wrapper chính với navigation và sidebar
- `Login.vue`: Trang đăng nhập với form validation
- `admin/`: Các trang quản trị (dashboard, user management, reports)
- `student/`: Các trang dành cho sinh viên (profile, courses, grades)
- `teacher/`: Các trang dành cho giáo viên (class management, attendance)

#### **Routers Module** (`src/routers/`)
- Cấu hình routing với guards cho authentication
- Lazy loading cho performance optimization
- Role-based access control

## 📜 Scripts có sẵn

```json
{
  "dev": "vite",                    // Chạy development server
  "build": "vue-tsc -b && vite build", // Build production với type checking
  "preview": "vite preview"         // Preview bản build locally
}
```

### Development Commands

```bash
# Chạy development server với hot reload
npm run dev

# Build và type check
npm run build

# Preview production build
npm run preview

# Cài đặt dependencies mới
npm install <package-name>

# Cập nhật dependencies
npm update
```

## 🛠 Công nghệ sử dụng

| Công nghệ | Version | Mô tả |
|-----------|---------|-------|
| Vue.js | 3.5.13 | Progressive JavaScript Framework |
| TypeScript | 5.7.2 | Typed JavaScript |
| Vite | 6.2.0 | Next Generation Frontend Tooling |
| Ant Design Vue | 4.2.6 | Enterprise UI Components |
| TailwindCSS | 4.1.3 | Utility-first CSS Framework |
| Pinia | 3.0.2 | Vue Store Pattern |
| Vue Router | 4.5.0 | Official Router for Vue.js |
| Axios | 1.9.0 | Promise-based HTTP Client |
| Firebase | 11.8.0 | Backend-as-a-Service Platform |
| Day.js | 1.11.13 | Lightweight Date Library |

## ⚙️ Cấu hình

### Environment Variables

Tạo file `.env` trong thư mục root:

```env
# API Configuration
VITE_API_BASE_URL=http://localhost:8080/api
VITE_API_TIMEOUT=10000

# Firebase Configuration
VITE_FIREBASE_API_KEY=your_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=123456789
VITE_FIREBASE_APP_ID=your_app_id
```

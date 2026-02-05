# Tire Management Android App

A comprehensive mobile application for managing tire data and vehicle maintenance in a fleet management system. Built with React Native and Expo, this app provides role-based access for drivers, employees, and administrators to track and manage tire conditions, vehicle data, and maintenance schedules.

## 📱 Features

### Core Functionality
- **User Authentication**: Secure login system with Firebase Authentication
- **Role-Based Access Control**: Three distinct user roles (Driver, Employee, Admin)
- **Tire Data Management**: Input and view comprehensive tire data
- **Vehicle Management**: Track and view vehicle information
- **Tire Check List**: Maintain and track tire inspection checklists
- **Profile Management**: Edit user profiles with picture upload capability
- **Push Notifications**: Real-time notifications for important updates
- **Dark Mode Support**: Toggle between light and dark themes
- **Multi-language Support**: Internationalization ready
- **Remember Me**: Auto-login functionality for returning users

### User Roles

#### 🚗 Driver
- View tire and vehicle data
- Access basic tire management features
- Receive notifications about tire conditions

#### 👷 Employee
- Full tire data entry and viewing capabilities
- Complete tire checklist management
- Vehicle data access
- Profile editing

#### 👨‍💼 Admin
- Full access to all features
- Tire management (input/view/checklist)
- Vehicle management
- Administrative controls
- Settings management

## 🛠️ Tech Stack

- **Framework**: React Native (v0.74.3)
- **Build Tool**: Expo (v51.0.22)
- **Language**: TypeScript (v5.1.3)
- **Navigation**: React Navigation (Native Stack)
- **Backend**: Firebase
  - Authentication
  - Realtime Database
  - Cloud Messaging
- **State Management**: React Context API
- **UI Components**: React Native Elements
- **Notifications**: Expo Notifications & React Native Push Notification
- **Storage**: AsyncStorage
- **Image Handling**: Expo Image Picker

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- Node.js (v14 or higher)
- npm or yarn
- Expo CLI (`npm install -g expo-cli`)
- Android Studio (for Android development) or Xcode (for iOS development)
- A Firebase account and project

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/janithjay/TiremanagementAndroidApp.git
   cd TiremanagementAndroidApp
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure Firebase**
   
   The Firebase configuration is located in `FirebaseConfig.ts`. Update it with your Firebase project credentials:
   ```typescript
   const firebaseConfig = {
     apiKey: "YOUR_API_KEY",
     authDomain: "YOUR_AUTH_DOMAIN",
     projectId: "YOUR_PROJECT_ID",
     storageBucket: "YOUR_STORAGE_BUCKET",
     messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
     appId: "YOUR_APP_ID",
     measurementId: "YOUR_MEASUREMENT_ID"
   };
   ```

4. **Set up Firebase Database**
   
   Ensure your Firebase Realtime Database has the following structure:
   ```
   - UserauthList
     - {userId}
       - firstName
       - lastName
       - email
       - occupation (driver/employee/admin)
       - profilePicture
   - TireData
   - VehicleData
   ```

## 🏃 Running the App

### Development Mode

Start the Expo development server:
```bash
npm start
```

### Run on Android
```bash
npm run android
```

### Run on iOS
```bash
npm run ios
```

### Run on Web
```bash
npm run web
```

## 📁 Project Structure

```
TiremanagementAndroidApp/
├── app/
│   └── screens/
│       ├── AdminHome.tsx          # Admin dashboard
│       ├── DriverHome.tsx         # Driver dashboard
│       ├── EmployeeHome.tsx       # Employee dashboard
│       ├── Login.tsx              # Login screen
│       ├── TireManagement.tsx     # Tire management hub
│       ├── VehicleManagement.tsx  # Vehicle management hub
│       ├── EnterData.tsx          # Tire data entry form
│       ├── ViewData.tsx           # View tire data
│       ├── ViewVehicle.tsx        # View vehicle data
│       ├── TireCheckList.tsx      # Tire inspection checklist
│       ├── ProfileEdit.tsx        # User profile editor
│       ├── Settings.tsx           # App settings
│       ├── DarkModeContext.tsx    # Dark mode state management
│       ├── notificationContext.tsx # Notification state management
│       ├── translations.tsx       # Multi-language support
│       ├── Header.tsx             # Reusable header component
│       ├── Footer.tsx             # Reusable footer component
│       ├── NavBar.tsx             # Navigation bar component
│       └── images/                # Image assets
├── assets/                        # App assets (icons, splash screen)
├── App.tsx                        # Main app component
├── FirebaseConfig.ts              # Firebase configuration
├── app.json                       # Expo configuration
├── package.json                   # Dependencies
└── tsconfig.json                  # TypeScript configuration
```

## 🔐 Authentication Flow

1. User enters email and password
2. Firebase Authentication validates credentials
3. System retrieves user occupation from Realtime Database
4. User is redirected to appropriate home screen based on role:
   - Driver → DriverHome
   - Employee → EmployeeHome
   - Admin → AdminHome

## 🎨 Theming

The app supports both light and dark modes. Users can toggle between themes in the Settings screen. The theme preference is managed through the `DarkModeContext` and persists across app sessions.

## 📱 Push Notifications

The app implements push notifications using:
- Expo Notifications for cross-platform support
- Firebase Cloud Messaging for backend delivery
- Background fetch for periodic updates

Notifications are configured to:
- Show alerts
- Play sounds
- Update badge counts

## 🌍 Internationalization

The app includes a translation system (`translations.tsx`) that supports multiple languages, making it easy to add new languages or modify existing translations.

## 🔧 Configuration Files

- **app.json**: Expo configuration including app name, version, and platform-specific settings
- **eas.json**: EAS Build configuration for production builds
- **tsconfig.json**: TypeScript compiler options
- **babel.config.js**: Babel configuration for JavaScript transpilation
- **metro.config.js**: Metro bundler configuration

## 📝 Building for Production

### Using EAS Build

1. Install EAS CLI:
   ```bash
   npm install -g eas-cli
   ```

2. Login to Expo:
   ```bash
   eas login
   ```

3. Configure your build:
   ```bash
   eas build:configure
   ```

4. Build for Android:
   ```bash
   eas build --platform android
   ```

5. Build for iOS:
   ```bash
   eas build --platform ios
   ```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is private and proprietary.

## 👥 Authors

- [@janithjay](https://github.com/janithjay)

## 🐛 Known Issues

- Firebase debug log is currently committed to the repository and should be added to `.gitignore`

## 📞 Support

For support, please open an issue in the GitHub repository or contact the development team.

## 🔄 Version History

- **v1.0.0** - Initial release
  - User authentication
  - Role-based access control
  - Tire and vehicle management
  - Push notifications
  - Dark mode support

## 🙏 Acknowledgments

- React Native community
- Expo team
- Firebase documentation
- All contributors and testers

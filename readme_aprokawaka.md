# Aprokawaka App

Aprokawaka is a mobile application designed to keep users informed about the current state of their environment. It collects and analyzes data such as news, weather updates, and crisis alerts, providing real-time notifications tailored to the user’s location.

---

## **Features**

### **Core Features**
- **Real-Time Location-Based Updates**:
  - Tracks user’s current location via GPS.
  - Delivers tailored updates on news, weather, and potential crises.
- **Customizable Notifications**:
  - Users can add specific locations (e.g., home, workplace, farm) for personalized updates.
- **AI-Powered Insights**:
  - Predicts potential events based on data patterns.
  - Analyzes news for relevant highlights.
- **Interactive Dashboard**:
  - Visualizes data with heatmaps and graphs.
  - Provides quick access to updates for multiple locations.
- **Google AdMob Integration**:
  - Monetization through banner and interstitial ads.

### **Planned Features**
- **Subscription Plan** (currently inactive):
  - Ad-free experience.
  - Priority updates and insights.
  - Premium user support.

---

## **Technology Stack**

### **Frontend**
- React Native with TypeScript.
- Key libraries: 
  - `expo-location` (location tracking).
  - `expo-notifications` (notifications).
  - `react-native-maps` (maps and geolocation).

### **Backend**
- Supabase for database and authentication.
- Real-time data synchronization.

### **APIs**
- **Google News API**: News updates.
- **OpenWeatherMap API**: Weather data.
- **Google Maps API**: Geolocation services.
- **EONET or CrisisNET**: Crisis and disaster alerts.

### **AI Tools**
- NLP for news summarization.
- Predictive analytics for alert generation.

---

## **Setup Instructions**

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/aprokawaka.git
   ```
2. Navigate to the project directory:
   ```bash
   cd aprokawaka
   ```
3. Install dependencies:
   ```bash
   npm install
   ```
4. Set up environment variables:
   - `SUPABASE_URL`
   - `SUPABASE_ANON_KEY`
   - API keys for Google, OpenWeatherMap, and EONET.
5. Start the development server:
   ```bash
   expo start
   ```

---

## **Database Schema**

### **Users Table**
| Column       | Type      | Description                  |
| ------------ | --------- | ---------------------------- |
| `id`         | UUID      | Unique identifier for users. |
| `email`      | String    | User’s email address.        |
| `password`   | String    | Encrypted password.          |
| `created_at` | Timestamp | Registration date.           |

### **User Locations Table**
| Column          | Type      | Description                             |
| --------------- | --------- | --------------------------------------- |
| `id`            | UUID      | Unique identifier.                      |
| `user_id`       | UUID      | References the user in the Users table. |
| `location_type` | String    | e.g., Current, Home, Work, Farm.        |
| `latitude`      | Float     | Latitude of the location.               |
| `longitude`     | Float     | Longitude of the location.              |
| `preferences`   | JSON      | User-defined update preferences.        |
| `created_at`    | Timestamp | Timestamp when the location was added.  |

### **Alerts Table**
| Column        | Type      | Description                                |
| ------------- | --------- | ------------------------------------------ |
| `id`          | UUID      | Unique identifier for alerts.              |
| `location_id` | UUID      | References the location in User Locations. |
| `alert_type`  | String    | News, Weather, Crisis, etc.                |
| `content`     | Text      | Details of the alert.                      |
| `timestamp`   | Timestamp | When the alert was generated.              |

---

## **Contributing**

We welcome contributions to improve Aprokawaka! Please follow these steps:

1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add feature-name"
   ```
4. Push the branch:
   ```bash
   git push origin feature-name
   ```
5. Open a pull request.

---

## **License**

This project is licensed under the MIT License. See the LICENSE file for details.

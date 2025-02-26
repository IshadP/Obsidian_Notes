# Idea:
Our college is far away from city, so some student travel by there own vehicle (2 wheelers / 4 wheelers), consider this group of people as group A, others take the help of public transport like metro and city bus, consider this people as group B.
For students who travel by metro they have to land at nearest metro station which is 2 km away from college, from there they travel by city bus. The idea is to build a app so that, these people of group B can ping people of group A for ride along till college, with half or no compensation based on driver's will.

## Common Questions:

### 1. **Why Would Drivers Pick Someone Up With Minimal Incentives?**

To encourage drivers, the app needs to provide non-monetary and practical incentives:

- **Community Building**: Highlight the idea of helping fellow students. Students may feel more inclined to participate in a friendly, college-specific initiative.
- **Recognition and Rewards**:
    - **Leaderboards**: Drivers can earn points for each ride, leading to a "Top Helpers" list.
    - **Badges**: Award achievements for frequent participation (e.g., "Campus Hero").
- **Fuel Sharing**: Option for passengers to offer partial compensation for fuel, in line with driver's preferences.
- **Convenience Factor**: Match requests with drivers who are already passing by the metro station to avoid significant route deviation.

---

### 2. **Notification Without Distracting Drivers**

For two-wheeler drivers, safety is critical. Here's how notifications can be managed:

- **Pre-Ride Notifications**:
    - Allow drivers to **pre-schedule their availability** for specific days/times. Notifications can be sent when a ride request matches their schedule.
- **Smart Notifications**:
    - Notify drivers **before they start driving**, based on the passenger’s estimated arrival time at the pickup point. For instance, "Student X will be at Metro Station in 10 minutes."
    - Drivers can accept or decline before starting their journey.
- **Hands-Free Alerts**:
    - Use **voice alerts** through the phone’s speaker or Bluetooth headphones to inform drivers of new requests.
    - Example: "You have a ride request from Metro Station. Check when safe to respond."
- **No Real-Time Matching While Driving**:
    - Ensure drivers don't need to use the app during the ride. Any matches should be finalized **before the journey starts**.

---

### 3. **Preventing Unauthorized Pickups**

Ensuring the driver picks up only the assigned person is crucial for trust:

- **Identity Verification**:
    - Assign **unique codes** to passengers for the driver to verify upon pickup (like OTP).
    - Example: Passenger says, "My code is 1234," and the driver confirms it.
- **Photo Profiles**:
    - Both drivers and passengers have profile pictures visible in the app to identify each other at pickup.
- **Rating System**:
    - Drivers and passengers rate each other after each ride. Unauthorized pickups or bad experiences can lower a driver’s rating.
- **Clear Policy**:
    - Establish clear rules in the app about unauthorized pickups, including consequences for repeated violations (e.g., temporary suspension).

---

### 4. **Using Existing Vehicles**

- This aligns well with the idea. Students will use their own vehicles, and the app will focus solely on coordination.
- **Optimization Features**:
    - Drivers can indicate whether they are on a two-wheeler or four-wheeler to match with appropriate passenger numbers (e.g., two-wheelers can accept one passenger, while four-wheelers can accept more).

---

### Additional Features to Consider

1. **Safety and Trust**:
    
    - College email or ID verification for app registration to ensure only genuine students use the app.
    - Emergency contact feature for passengers and drivers.
2. **Route Optimization**:
    
    - Allow drivers to view a heatmap of active requests to plan routes more effectively.
3. **Privacy Control**:
    
    - Drivers can choose to accept or decline requests without revealing personal details like phone numbers.

---
# Technologies

### **1. Frontend**

**Technologies for Design and Frontend Development**

- **React Native**: Core framework for building cross-platform mobile applications.
- **Expo**: For simplifying development, debugging, and deployment of React Native apps.
- **React Native Paper**: UI component library for building Material Design components.
- **Figma/Adobe XD**: For UI/UX design and prototyping.
- **React Navigation**: For handling app navigation (stack, tab, and drawer navigation).
- **Styled Components** or **CSS-in-JS**: For customized styling (optional if not relying solely on React Native Paper).

---

### **2. Data**

**Databases and Integration Tools for Data Management**

- **Firebase Realtime Database** or **Firestore**:
    - A NoSQL database for storing ride requests, user profiles, and notifications.
- **SQLite** (via `expo-sqlite`): For local offline data storage, like ride history.
- **REST API or GraphQL** (Apollo Client for GraphQL): For communication between frontend and backend.
- **Axios** or **Fetch API**: For API calls in React Native.
- **Cloudinary** or **Firebase Storage**: For storing profile pictures or other media assets.

---

### **3. Backend**

**Tools and Frameworks for Making the App Functional**

- **Node.js** with **Express.js**: For building the server-side application.
- **Firebase Cloud Functions**: Optional lightweight backend for simple serverless operations like sending notifications.
- **MongoDB** (via Atlas) or **PostgreSQL**: For a robust backend database if Firebase is not used.
- **Socket.IO**: For real-time ride request updates and notifications.
- **OneSignal**: For push notifications to drivers and passengers.
- **Google Maps API**:
    - Geolocation services for mapping metro station to college routes.
    - Suggesting nearby drivers based on proximity.
- **Twilio** or **SendGrid**: For SMS or email notifications, if required.

---

### **4. Others**

**Additional Tools and Services**

- **Git/GitHub**: For version control and collaboration.
- **Expo Notifications API**: For sending push notifications directly through Expo.
- **Jest** or **Mocha**: For testing the app (unit and integration tests).
- **ESLint/Prettier**: For maintaining code quality and consistent formatting.
- **Google Firebase Authentication**: For secure login using college email IDs.
- **Environment Configuration Tools**:
    - **dotenv**: For storing environment variables securely.
    - **Expo Constants**: For managing app-specific constants.
- **Google Cloud Platform (GCP)** or **AWS**: For deploying the backend and handling storage (optional, depending on scale).
- **Expo EAS (Expo Application Services)**: For building and deploying your app to Android/iOS stores.

---


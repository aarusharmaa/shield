Shield: Your Safety Web Platform
Shield is a comprehensive web application designed to empower individuals during emergencies by providing real-time disaster alerts, smart navigation, one-click SOS functionality, trusted contact management, and shared status updates. 

1. Features Implemented
Here's a breakdown of the key features implemented in Shield, along with their estimated difficulty levels:

- Dark Mode Support (Easy)
Applications that provide a dark mode, based on user preference.

- Dynamic Theming Based on API Data:(Medium)
Responsive design for seamless experience across desktop, tablet, and mobile devices.
Clean, intuitive layout with distinct sections for different functionalities.
Dynamic theming (Light Mode, Dark Mode, High Contrast Mode).

-Multilingual Support (Medium)
Supports English, Hindi, and Spanish for key UI texts.
Language switcher for easy toggling.

-The Story Mode (Medium)
Guided tour explaining key features of the application.
Highlights relevant sections during the tour.

-Voice Navigation and Accessibility Features (Hard)
High Contrast Mode for improved visibility.
Dark/Light Theme
Text-to-Speech (TTS) for reading out section content.
Voice Commands for hands-free interaction (e.g., "SOS", "Refresh Alerts", "Read Alerts").

-Text-to-Speech for Content (Hard)
Text-to-Speech (TTS) for reading out section content.
Voice Commands for hands-free interaction (e.g., "SOS", "Refresh Alerts", "Read Alerts").

-Parallel Interaction Mode:
Applications that allow two users to interact within the app at the same time. This includes real-time shared input.



2. API(s) Used
Shield leverages several APIs to deliver its functionality:

-Google Maps JavaScript API:
Purpose: For displaying interactive maps, user location, custom markers (danger zones, safe zones), and calculating/rendering driving directions.

OpenWeatherMap API:
Purpose: To fetch current weather conditions based on user's location, enabling dynamic theming of the application.

Twilio (Simulated):
Purpose: Conceptually for sending SMS alerts to trusted contacts during an SOS event.

3. Screenshots
Here are some screenshots showcasing the Shield application:
<img width="1440" alt="Screenshot 2025-07-05 at 9 14 43 PM" src="https://github.com/user-attachments/assets/c9bafb6f-eae8-4fa5-b7d0-bbcf0efd0c23" />


Homepage / Alerts Section
Displays real-time disaster alerts and the refresh button.
<img width="1440" alt="Screenshot 2025-07-05 at 9 14 43 PM" src="https://github.com/user-attachments/assets/59acca2e-457d-4829-ba0e-c345c6e7e584" />


Map Section with Safe Route
Shows user location, danger zones, and a calculated safe route.
<img width="1440" alt="Screenshot 2025-07-05 at 9 15 56 PM" src="https://github.com/user-attachments/assets/e5a2d847-9db5-4670-b018-81528503289a" />


SOS Button
The prominent one-click emergency SOS button.
<img width="1440" alt="Screenshot 2025-07-05 at 9 16 31 PM" src="https://github.com/user-attachments/assets/a934e1ac-d272-422a-8d81-4fe50fa87378" />


Trusted Contacts Management
Interface for adding and managing emergency contacts.
<img width="1440" alt="Screenshot 2025-07-05 at 9 17 03 PM" src="https://github.com/user-attachments/assets/41c80f38-1b77-4488-83d6-346e769e678e" />


Shared Status Updates
The public message feed for real-time community updates.
<img width="1440" alt="Screenshot 2025-07-05 at 9 17 53 PM" src="https://github.com/user-attachments/assets/83dd8fde-b273-4c19-ae75-144906b4c61b" />


Dark Mode / High Contrast Mode
An example of the application in Dark Mode.
<img width="1440" alt="Screenshot 2025-07-05 at 9 18 18 PM" src="https://github.com/user-attachments/assets/dc9420d7-be54-46fb-8350-fd29fae99d8b" />
<img width="1440" alt="Screenshot 2025-07-05 at 9 18 21 PM" src="https://github.com/user-attachments/assets/e10529b1-415a-4077-af9a-8071f079d184" />



4. Setup and Testing Instructions
To run Shield locally and test its functionalities, follow these steps:

Prerequisites
Web Browser: A modern web browser (Google Chrome is recommended for full Web Speech API support).

Google Maps API Key:
Go to Google Cloud Console.
Create a new project or select an existing one.
Navigate to "APIs & Services" -> "Library".
Search for and enable "Maps JavaScript API".
Go to "APIs & Services" -> "Credentials".
Create a new API Key. Restrict this API key to your domain (e.g., localhost:port for local development) and to the "Maps JavaScript API" to prevent unauthorized use.

OpenWeatherMap API Key:
Go to OpenWeatherMap.
Sign up for a free account.
Your API key will be available in your account dashboard. Note that it might take a few minutes for a new API key to become active.


Locate const GOOGLE_MAPS_API_KEY = 'AIzaSyBy3rkdHLTh-WOR2x18SpzVHjw9w4w-FaM'; (around line 900). Replace the placeholder value with your actual Google Maps API Key.
Locate const OPENWEATHER_API_KEY = '897ca075931405ab51b2a14a8e8dc211'; (around line 1050). Replace the placeholder value with your actual OpenWeatherMap API Key.


Open in Browser: Open the index.html file directly in your web browser. You can usually do this by double-clicking the file or by dragging it into your browser window.

Testing Instructions
Initial Load:

Observe the loading overlay.
The app should load and display the main sections (Alerts, Map, SOS, Contacts, Shared Status).
If Firebase keys are incorrect, you will see console warnings and contact/message features will not work. If Google Maps key is incorrect, the map will show an error.

Theme Toggles:

Click the "Light Mode" / "Dark Mode" toggle to switch themes.
Click the "High Contrast" toggle to activate/deactivate high contrast mode.
Observe if the app's theme changes dynamically based on your location's weather (if OpenWeatherMap API key is active).

Language Switcher:
Select different languages from the dropdown (English, Hindi, Spanish).
Verify that the UI text updates accordingly.

Disaster Alerts:
The "Real-Time Disaster Alerts" section should show simulated alerts.
Click "Refresh Alerts" to re-fetch (simulated) alerts.
Click the "Read Section" button next to the title to hear the section content read aloud.

Smart Navigation & Map:
Upon loading, the browser will likely ask for your location. Allow it.
The map should center on your location (blue marker).
You should see red markers for simulated danger zones and a yellow marker for a simulated "Safe Zone."
A green marker indicates the start of the safe route.
A route should be drawn from your location to the "Safe Zone."
If geolocation is denied or fails, the map will default to Bhopal, India.
Click the "Read Section" button next to the title to hear the section content read aloud.

One-Click Emergency SOS:
Click the large "SOS" button.
A "SOS sent successfully (simulated)!" message should appear.
Click the "Read Section" button next to the title to hear the section content read aloud.

Trusted Emergency Contacts:
In the "Add Contact" form, enter a name and a phone number (e.g., +1234567890). Ensure the phone number starts with + and contains only digits.
Click "Add Contact."
A "Contact added successfully!" message should appear, and the contact should appear in the list below.
Refresh the page; the contact should persist (due to Firebase Firestore).
Click the "Delete" button next to a contact to remove it.
Click the "Read Section" button next to the title to hear the section content read aloud.

Shared Status Updates:
Type a message in the input field and click "Send."
The message should appear in the message feed immediately.
If another user (or you in another browser tab/window) sends a message, it should appear in real-time in your feed.
Click the "Read Section" button next to the title to hear the section content read aloud.

Voice Commands:
Click the "Voice Commands" button.
Your browser will ask for microphone permission. Allow it.
A message "Voice commands active..." should appear.
Try saying commands like: "SOS", "Refresh Alerts", "Read Alerts", "Read Map", "Read SOS", "Read Contacts", "Read Shared Status".
Observe the corresponding actions or messages.
Click the "Voice Commands" button again to stop listening.

Interactive Tutorial:
Click the "Start Tour" button in the header.
Follow the prompts using "Next" and "Previous" buttons.
Observe how different sections are highlighted as the tour progresses.
Click "Skip Tour" to end the tutorial at any time.


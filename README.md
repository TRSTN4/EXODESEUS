
![](https://github.com/TRSTN4/EXODESEUS_APP/blob/main/images/exodeseus_banner.png?raw=true)

**What is included?** \
-- *What is EXODESÉUS and how does it work?* \
-- *App Preview*

---

**What is EXODESÉUS and how does it work?** \
EXODESÉUS is a comprehensive application designed to deliver real-time news updates and offer emergency response features. This document outlines the app's core functionalities, including news retrieval and publication, emergency alert system, and user interaction with the platform. The app is available on both iOS and Android platforms, with the iOS version developed in Swift and the Android version in Kotlin. 

---

1.  **News Articles Handling** \
\
**1.1 Data Collection** \
The application leverages a Raspberry Pi to scrape news content from various sources such as Sky News, LiveUaMap, and others. The collected data is then formatted and sent to a centralized API (Running on Google Cloud Platform). \
\
**1.2 Storing Articles in Database** \
Upon receiving the data from the Raspberry Pi, the API processes and stores the news articles in a database. This ensures that the latest news updates are readily available for user retrieval.

![](https://github.com/TRSTN4/EXODESEUS_APP/blob/main/images/news_source_data_flow.png?raw=true)

---

2. **Retrieval by Users** \
When a user opens or refreshes the EXODESÉUS app, it makes a GET request to the API. The API then fetches the relevant news articles from the database, allowing the user to access up-to-date news information.

![](https://github.com/TRSTN4/EXODESEUS_APP/blob/main/images/user_interaction_with_news.png?raw=true)

---

3. **User-Generated Content** \
Users can contribute their own news articles or messages through the app. This is achieved by making a POST request from the app, which includes the user's message. The API receives this content and stores it in the database, making it available for other users to view.

![](https://github.com/TRSTN4/EXODESEUS_APP/blob/main/images/user_generated_content.png?raw=true)

---

4. **Emergency Response Features (SOS)** \
\
_* Currently for selected households only._ \
\
**3.1 SOS Functionalities** \
The app includes an SOS tab that integrates with various hardware and services, including Hue lights and Sonos speakers, through Firebase. Each hardware has corresponding values in Firebase that is monitored by the Raspberry Pi. \
\
**3.2 Activation Process** \
*When an SOS feature is activated from the app:* \
--   The app changes the required values in Firebase.\
--   The Raspberry Pi detects these changes and executes the relevant scripts to trigger alarms using the connected Sonos speakers and Hue lights. \
\
**3.3 Alert to All Users** \
Upon activation of the SOS feature, all users of the app receive a notification and the app interface switches to a "CODE RED ALERT" screen. This emergency mode restricts access to other app functionalities to ensure focus on the emergency. \
\
**3.4 Resolution of Alert** \
To exit the CODE RED ALERT, a unanimous decision to deactivate the alert is required from the users. This voting mechanism is designed to prevent misuse and ensure that the SOS feature is used only during genuine emergencies.

![](https://github.com/TRSTN4/EXODESEUS_APP/blob/main/images/sos_functionality_and_response.png?raw=true)

---

5. **Threat Monitoring** \
The Raspberry Pi continuously monitors for potential threats, including changes in DEFCON levels, 24/7. If a change to DEFCON 1 is detected, the system automatically activates the CODE RED ALERT across the platform without user intervention. Additionally, every first Monday of the month at 12 PM, the system conducts a monthly system-check test that runs for exactly 1 minute and 26 seconds to ensure all systems are operational.

![](https://github.com/TRSTN4/EXODESEUS_APP/blob/main/images/defcon_level_monitoring_and_response.png?raw=true)

---

6. **Notifications** \
Users can opt-in to receive specific notifications through the app. Upon enabling notifications, the app connects to Firebase and registers the user's Firebase Cloud Messaging (FCM) token. These tokens are then used to deliver notifications as needed.

---

7. **Access and Security** \
EXODESÉUS is a closed application, accessible only via invite keys. This exclusivity ensures that personal details of the users are safeguarded as each invite key contains sensitive information about the invitee. The app is currently available to selected households only, maintaining privacy and security at the forefront of its operations. Despite its closed nature, the application architecture allows for rapid public release if the need arises.

---

8. **Conclusion** \
EXODESÉUS integrates complex news delivery systems with robust emergency response functionalities, providing a unique and valuable service to its users. Through intelligent hardware integration and user interaction, the app ensures timely delivery of news and effective response in emergencies, all while maintaining a secure and exclusive environment for its users.

---

**App Preview**

-   **Browse Automatically Posted Articles**: View a continuous feed of war-related articles that are automatically uploaded to the app. Scroll to discover extensive content.<br><img src="https://github.com/TRSTN4/EXODESEUS/blob/main/images/EXODESEUS_FRONT.gif?raw=true" width="200" height="auto"> 

-   **Visual Examples of Articles**: Here are some visual examples to demonstrate how the articles are displayed within the app:<br><img src="https://github.com/TRSTN4/EXODESEUS/blob/main/images/EXODESEUS_PREVIEW1.gif?raw=true" width="200" height="auto"> <img src="https://github.com/TRSTN4/EXODESEUS/blob/main/images/EXODESEUS_PREVIEW2.gif?raw=true" width="200" height="auto"> <img src="https://github.com/TRSTN4/EXODESEUS/blob/main/images/EXODESEUS_PREVIEW3.gif?raw=true" width="200" height="auto"> 

-   **Create and Update Messages**: Users can instantly post messages within the app and update them anytime as new information becomes available.<br><img src="https://github.com/TRSTN4/EXODESEUS/blob/main/images/EXODESEUS_SEND_POST.gif?raw=true" width="200" height="auto"> <img src="https://github.com/TRSTN4/EXODESEUS/blob/main/images/EXODESEUS_EDIT_POST.gif?raw=true" width="200" height="auto">
    
-   **Filter Articles by Category**: At the top bar, select a specific category to filter the news feed, displaying only articles relevant to that category.<br><img src="https://github.com/TRSTN4/EXODESEUS/blob/main/images/EXODESEUS_SLIDE_NAVIGATION.gif?raw=true" width="200" height="auto"> 
    
-   **Access Source Information**: The app automatically adds news and intel articles. To know more about the source of any article, users can click the 'Source' button located at the top right of each article.<br><img src="https://github.com/TRSTN4/EXODESEUS/blob/main/images/EXODESEUS_SOURCE.gif?raw=true" width="200" height="auto"> 
    
-   **Manage Notifications by Category**: Within the notification tab, users can easily toggle on and off notifications for specific news categories according to their preferences.<br><img src="https://github.com/TRSTN4/EXODESEUS/blob/main/images/EXODESEUS_NOTIFICATIONS.gif?raw=true" width="200" height="auto"> 
    
-   **Enable Red Alert on Hue Lights**: Use the SOS tab to activate a red alert across all connected Hue lights for immediate attention in emergencies. *(Only available to households with Philips Hue)*<br><img src="https://github.com/TRSTN4/EXODESEUS/blob/main/images/EXODESEUS_HUE_ACTIVATION.gif?raw=true" width="200" height="auto"> <img src="https://github.com/TRSTN4/EXODESEUS/blob/main/images/EXODESEUS_HUE_RED_ALERT.gif?raw=true" width="200" height="auto"> 
 
-   **Activate Panic Mode on Sonos Devices**: In the SOS tab, users can initiate Panic Mode to play an SOS signal through all connected Sonos speakers, enhancing the urgency of alerts. *(Only available to households with Sonos devices)*<br><img src="https://github.com/TRSTN4/EXODESEUS/blob/main/images/EXODESEUS_SONOS_ACTIVATION.gif?raw=true" width="200" height="auto"> 
 
-   **Engage Comprehensive SOS Mode**: In critical situations, users can activate SOS mode which will enable all connected Hue and Sonos devices in panic mode, lock the app in SOS mode for all household members, and send notifications to ensure everyone is alerted.<br><img src="https://github.com/TRSTN4/EXODESEUS/blob/main/images/EXODESEUS_SOS.gif?raw=true" width="200" height="auto"> 
 
-   **Log SOS Feature Activity**: When any SOS related feature is activated or deactivated, the app will record and log this activity for future reference.<br><img src="https://github.com/TRSTN4/EXODESEUS/blob/main/images/EXODESEUS_SOS_ALERTS.gif?raw=true" width="200" height="auto"> 

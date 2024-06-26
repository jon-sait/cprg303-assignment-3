# Assignment: Architectural Decisions

## Scenario 1

### Native, web, or hybrid app

#### Context

The mobile app for the retail company requires features like offline mode, push notifications, and localization for international expansion.

#### Options considered

1. Native app
2. Web app
3. Hybrid app

#### Decision

Native app

#### Rationale

A native app provides the best user experience and performance, especially for features like offline browsing and push notifications. Native development allows for more efficient use of device capabilities, which aligns with the need for a seamless and responsive user experience, especially in handling image-intensive product catalogs. Additionally, native apps better support localization, important for international expansion.

#### Consequences

This choice requires more investment in development and maintenance, as platform-specific code need to be maintained even when using cross-platform frameworks. However, the benefits in performance, user experience, and access to device features outweigh the costs.

#### Conclusion

A native app will best serve the company's needs, offering superior performance, a better user experience, and the flexibility needed to support the app's complex features.

### UI Framework

#### Context

The application needs a robust UI framework that supports rich, interactive, and responsive designs to enhance the user experience.

#### Options considered

1. SwiftUI (for iOS)
2. Jetpack Compose (for Android)
3. React Native (for hybrid)

#### Decision

React Native

#### Rationale

Using a cross-platform framework provides a seamless user experience across all platforms. It also lowers development costs and shortens development cycles.

#### Consequences

Part of the downside of developing a native app is hedged by using a cross-platform UI framework, ensuring a smooth user experience without unnecessarily delaying product delivery.

#### Conclusion

Using React Native for the app UI is the best strategy to achieve a high-quality and optimized user interface.

### Backend language

#### Context

The backend needs to efficiently handle requests from mobile clients, including data processing for product information, order handling, and analytics.

#### Options considered

1. Node.js
2. Python with Django
3. C# with .NET Core

#### Decision

Node.js

#### Rationale

Node.js offers excellent performance for I/O intensive operations, which suits the mobile app's need for real-time data processing for features like order tracking and loyalty program management.

#### Consequences

Choosing Node.js necessitates proficiency in JavaScript/TypeScript among developers but benefits from an active community and an abundance of third-party packages to accelerate development.

#### Conclusion

Node.js is the optimal choice for the backend, aligning with the app's need for efficient real-time data processing.

### Permissions

#### Context

The app requires access to certain device features and user data to support its functionalities.

#### Options considered

1. Location
2. Push Notifications
3. Internet

#### Decision

- Push Notifications: To inform users about order updates, new products, and offers.
- Internet: Necessary for data synchronization and online functionalities.

#### Rationale

Location permissions are not essential for the core functionality of the app. Push Notifications are crucial for keeping the customers engaged and informed, while Internet permission is obvious for the app to function, particularly for fetching product data, syncing offline data, and processing payments.

#### Consequences

Asking minimal permissions enhances user trust and avoids unnecessary privacy concerns.

#### Conclusion

Limiting permissions to Push Notifications and Internet balances functionality with privacy, aligning with user expectations and regulatory standards.

### Data storage

#### Context

The app requires storing user data, product information, order history, and loyalty program data, supporting both online and offline modes.

#### Options considered

1. SQLite
2. Firebase Firestore
3. MySQL

#### Decision

Firebase Firestore

#### Rationale

Firebase Firestore offers real-time synchronization across user devices and supports offline data storage and retrieval, which is essential for the offline functionality requirement. Its easy integration with other Firebase services, like Firebase Cloud Messaging for push notifications, enhances the app's capabilities.

#### Consequences

Choosing Firestore ties the app somewhat to the Firebase ecosystem but significantly reduces development complexity and time.

## Scenario 2

### Native, web, or hybrid app

#### Context

The application needs to be available to both iOS and Android users and must be able to operate offline.

#### Options considered

1. Native app
2. Web app
3. Hybrid app

#### Decision

We have chosen to develop a Hybrid app.

#### Rationale

Our decision to go with a Hybrid app is motivated by its cross-platform compatibility which is in line with our need to have the app support both iOS and Android. The ability of Hybrid applications to function both online and offline fulfills the requirement for the app to have offline capabilities - a crucial factor considering the unstable internet connection some students and professors may face.

#### Consequences

While a hybrid app offers a lot of benefits, some cost is in performance. Native apps can offer better performance and can better utilize device-specific features. However, we believe the trade-off in terms of development efficiency and accessibility justifies our decision.

#### Conclusion

Given our requirements, a Hybrid app offers both cross-platform and offline capabilities making it the most suitable choice.

### UI Framework

#### Context

The selected framework should offer efficient development process and accessibility while providing an appealing user interface.

#### Options considered

1. Bootstrap
2. React Native

#### Decision

We have decided to use React Native as our UI Framework

#### Rationale

React Native allows for developing native mobile apps using only JavaScript and React. This provides a solid base for building high-quality user interfaces.

#### Consequences

While React Native provides a wealth of features, the learning curve might be steep for developers who are not familiar with React. However, the promise of efficient development and maintainability justifies this choice.

#### Conclusion

React Native is the best option for us thanks to its efficiency in development.

### Backend language

#### Context

The backend language should support efficient development, performance, and be suitable for mobile applications

#### Options considered

1. JavaScript (Node.js)
2. Python
3. Ruby (Rails)

#### Decision

We have decided to use Node.js as our backend language.

#### Rationale

Node.js excels at handling concurrent requests, which is essential for a social networking app like ours catering to many users simultaneously. Also, since we are already using JavaScript (via React Native) on the front end, using Node.js (JavaScript) on the backend is good for language consistency.

#### Consequences

Node.js does not perform well with CPU-intensive workloads. However, given the nature of our app, we anticipate this is a limitation we can live with.

#### Conclusion

Considering the type of our application, Node.js provides the best mix of efficiency, performance, and ease of use.

### Permissions

#### Context

The app needs to integrate with an existing Active Directory system, enforcing the privacy and security standards of the university.

#### Options considered:

1. Location
2. Push Notifications
3. Biometrics

#### Decision

All of the above.

#### Rationale

Location permission is essential for a social network service, though it's best to only prompt users for permission at the time it's needed. Push notification is explicitly requested by the client. Biometrics allows secure storage of credentials, enhancing security and privacy.

#### Consequences

Many permissions are needed. User experience could be affected by the permission request dialogs.

#### Conclusion

These permissions are essential for the core features of the application, despite the potential implication on user experience.

### Data Storage

#### Context

The app must be accessible offline as well as online, hence necessitating a seamless data synchronisation mechanism.

#### Options considered

1. Firebase
2. SQLLite
3. Realm Database

#### Decision

Firebase was chosen mainly for its offline capabilities.

#### Rationale

Firebase offers both real-time database and storage and makes it easy to sync data for offline use. It keeps the data locally in the device while offline and synchronizes data when the application is online.

#### Consequences

While Firebase has many benefits, it is has some limitations like complex querying system. Such limitations can be managed with careful design and testing.

#### Conclusion

Firebase will be a great fit for our project with its offline synchronization, security and scalability.

### Additional Frameworks or Technology Stacks

#### Context

The application requires certain features such as push notifications and integration with external Active Directory for login

#### Options considered

1. Firebase Cloud Messaging (FCM)
2. Azure Active Directory
3. AWS Cognito

#### Decision

We decide to use the Firebase Cloud Messaging for push notifications and Azure Active Directory for secure and seamless login.

#### Rationale

FCM simplifies the process of sending notifications and messages. For secure login and access control, Azure Active Directory is a popular choice that is known for its security.

#### Consequences

Both Firebase Cloud Messaging and Azure Active Directory have certain limitations and charge for extensive usage. However, they are both widely used and supported, making troubleshooting simpler.

#### Conclusion

Considering the utility and features provided, FCM and Azure Active Directory are the best choices for our application.

## Scenario 3

### Native, web, or hybrid app

#### Context

The app requires high performance, access to device features like GPS for location tracking, and a smooth user experience for food ordering.

#### Options considered

1. Native App
2. Web App
3. Hybrid App

#### Decision

Hybrid App

#### Rationale

Hybrid apps provide the optimal balance between the performance of native apps and the flexibility of web apps. They allow for device features access and can offer a seamless user experience using frameworks like React Native. This approach will provide the needed performance for location tracking and interactive features while being relatively cost-effective and quicker to develop compared to a fully native application.

#### Consequences

While hybrid apps can access device features, they might still face performance issues compared to native apps.

#### Conclusion

For our needs, a hybrid app developed with React Native serves as a balanced choice, ensuring accessibility across different platforms, good performance, and access to necessary device features.

### UI Framework

#### Context

The need for a user-friendly and seamless ordering interface.

#### Options considered

1. Bootstrap
2. Tailwind CSS
3. Material-UI

#### Decision

Material-UI

#### Rationale

Material-UI provides rich component libraries specifically designed for React apps. Given React Native is chosen for our hybrid app, Material-UI will offer a consistent look and feel that aligns with modern UX principles.

#### Consequences

Choosing a specific UI library like Material-UI may limit customization compared to a more foundational framework like Bootstrap.

#### Conclusion

Material-UI will enable quick development of a user-friendly interface, fulfilling the need for an easy-to-navigate food ordering app.

### Backend language

#### Context

Need a scalable, efficient, and secure backend to handle user data, payment processing, and real-time updates.

#### Options considered

1. Python (Django)
2. JavaScript (Node.js)
3. Java (Spring Boot)

#### Decision

JavaScript (Node.js)

#### Rationale

Node.js allows building scalable and efficient real-time applications. It integrates well with React Native and can efficiently handle I/O-bound tasks, real-time order tracking, and seamless data syncing activities, which are crucial for the app.

#### Consequences

Choosing Node.js means we may need to manage performance issues as traffic increases.

#### Conclusion

Node.js paired with Express will provide a robust solution for the backend, supporting our app's real-time and data-intensive operations seamlessly.

### Permissions

#### Context

The app requires permissions to function effectively, especially for personalized services like location-based restaurant suggestions and notifications.

#### Options considered

1. Location access
2. Push notifications
3. Camera and Payment information

#### Decision

Location access, Push notifications

#### Rationale

Access to the device's location and the ability to send push notifications are crucial for providing personalized content and timely updates to users, enhancing the overall user experience.

#### Consequences

If not managed correctly, prompting users too early for permissions can lead to denial, affecting functionality. Therefore, it's important to request permissions contextually.

#### Conclusion

Implementing clever permission handling will be crucial to the functional and user acceptance success of the app.

### Data storage

#### Context

Need to securely store user data, order history, payment information, and restaurant details.

#### Options considered

1. MySQL
2. Firebase
3. MongoDB

#### Decision

Firebase

#### Rationale

Firebase offers a comprehensive suite of tools including real-time databases which facilitate synchronous updates, authentication services, and easy integration with mobile apps, making it ideal for handling user data and payment information securely and efficiently.

#### Consequences

Using Firebase might introduce vendor lock-in.

#### Conclusion

The benefits of Firebase, with its built-in security features, real-time capabilities, and scalability, outweigh the cons for this application, making it ideal for our data storage needs.

### Any additional frameworks or technology stacks

#### Context

Additional tools are needed to ensure robust app functionalities especially for integrating various external systems and managing real-time data.

#### Options considered

1. Redux for state management
2. Stripe for payment integration

#### Decision

Redux, Stripe

#### Rationale

Redux will help in managing the app's state efficiently across different components. Stripe is selected for its wide range of supported payment methods and ease of integration.

#### Consequences

These additional technologies will increase the complexity of the app which might affect its maintenance but given the functionalities they provide, they are essential.

#### Conclusion

Implementing these technologies will significantly contribute to robust, dynamic, and user-friendly application architecture, covering all aspects of functionalities required for a successful food ordering service.

## Scenario 4

### Native, web, or hybrid app

#### Context

Considering the need for real-time tracking, geolocation services, secure payments, and an engaging user interface for the modern transportation company's app, we must decide the most effective approach to app development: native, web, or hybrid.

#### Options considered

1. Native Application
2. Web Application
3. Hybrid Application

#### Decision

Native Application

#### Rationale

A native application offers the best performance and user experience, which is critical for real-time applications like a transportation app. It allows for better integration with device features such as GPS for geolocation services, secure hardware for payments, and push notifications for timely alerts.

#### Consequences

Higher development and maintenance costs due to separate codebases for iOS and Android.

#### Conclusion

Considering the requirements for real-time tracking, high performance, and device integration, a native app is the most suitable option for the transportation company's needs.

### UI Framework

#### Context

A user-friendly and responsive interface is crucial for the app's success. We need to select a UI framework that supports our decision to develop a native app while ensuring great user experience and developer productivity.

#### Options considered

1. SwiftUI for iOS and Jetpack Compose for Android
2. React Native
3. Flutter

#### Decision

SwiftUI for iOS and Jetpack Compose for Android

#### Rationale

SwiftUI and Jetpack Compose are modern, native UI frameworks that offer a declarative approach to building interfaces. They provide the most native experience, optimal performance, and are tightly integrated with their respective platforms.

#### Consequences

Development requires proficiency in both Swift and Kotlin, potentially increasing the learning curve for developers.

#### Conclusion

To offer the best user experience and performance, we will use SwiftUI for iOS development and Jetpack Compose for Android. This approach aligns with our decision to create a native app.

### Backend language

#### Context

A scalable, performant, and secure backend is essential for handling real-time location updates, payments, and user authentication.

#### Options considered

1. Python with Django
2. Node.js
3. Go

#### Decision

Node.js

#### Rationale

Node.js is well-suited for building real-time applications due to its non-blocking I/O model, which ensures efficient handling of concurrent requests.

#### Consequences

Requires expertise in JavaScript and asynchronous programming.

#### Conclusion

Given the app's need for real-time functionalities and scalability, Node.js is the ideal choice for the backend technology.

### Permissions

#### Context

The app requires access to specific device features and user data to offer its services, which necessitates determining the necessary permissions.

#### Options considered

1. Location Services
2. Push Notifications
3. Camera and Photo Library

#### Decision

The app will request the following permissions:

- Location Services
- Push Notifications
- Camera and Photo Library

#### Rationale

Continuous location tracking is essential for drivers to allow for accurate ride tracking and optimization. Passengers need location services when using the app to book or track their ride. Push notifications are necessary for alerting users about ride status, driver updates, and promotions. Access to the camera and photo library on the other hand is unnecessary.

#### Consequences

Users might have privacy concerns regarding always-on location tracking for drivers.

#### Conclusion

Requesting these permissions is essential for the app's functionality, but it's crucial to handle user data responsibly and transparently to maintain trust.

### Data storage

#### Context

Efficient and secure storage of user profiles, ride history, and payment information is fundamental to the app's performance and reliability.

#### Options considered

1. Firebase
2. PostgreSQL
3. MongoDB

#### Decision

Firebase

#### Rationale

Firebase offers a comprehensive set of features including real-time database, authentication, and hosting services. It supports real-time data synchronization, which is crucial for tracking location updates.

#### Consequences

Reliance on a cloud-based solution may raise concerns regarding privacy.

#### Conclusion

Firebase is chosen for its real-time data capabilities, authentication services, and scalability.

### Any additional frameworks or technology stacks

#### Context

To enhance the app's functionality and streamline development, we need to consider additional frameworks or technology stacks.

#### Options considered

1. Google Maps API for geolocation services
2. Stripe for payment processing
3. Socket.IO for real-time communication

#### Decision

- Google Maps API
- Stripe
- Socket.IO

#### Rationale

Google Maps API is selected for its accuracy, comprehensive data, and extensive features for mapping and routing. Stripe offers a secure and user-friendly payment infrastructure with broad payment method support. Socket.IO facilitates real-time, bidirectional communication between web clients and servers, essential for updating locations in real-time.

#### Consequences

Dependence on API providers requires careful management of API usage to control costs.

#### Conclusion

Integrating Google Maps API, Stripe, and Socket.IO will provide the necessary functionality for geolocation, payments, and real-time communication, greatly benefiting the app's user experience and operational efficiency.

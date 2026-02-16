CS 499 Computer Science Capstone – ePortfolio
Weight Tracking Application: Enhanced
This repository contains the capstone ePortfolio for CS 499 – Computer Science Capstone at Southern New Hampshire University. It showcases the progressive enhancement of a Weight Tracking Android Application, originally developed in CS 360 – Mobile Architecture and Programming, across three key areas of computer science.

Overview
The capstone project demonstrates growth in computer science by taking a single artifact — a Weight Tracking Android app — and enhancing it through three milestones. Each milestone targets a distinct area of the discipline while building on the work of the previous milestone, resulting in a fully modernized, architecturally sound, and cloud-connected application.

Original Artifact
Source: CS 360 – Mobile Architecture and Programming
Language: Java
Platform: Android (Room database, SQLite)
The original application allowed users to log in, record daily weight entries, set a goal weight, view weight history, and opt in to SMS notifications. It was built with a flat project structure, activity-centric logic, and a local SQLite database managed through Android Room.
Original features:

User registration and login
Daily weight entry logging
Goal weight tracking
Weight history display via RecyclerView
SMS permission handling for notifications

Enhancement One – Software Design and Engineering
Milestone 2 | Focus: Architecture, language migration, and security
The application was migrated from Java to Kotlin and restructured to follow the MVVM (Model-View-ViewModel) architectural pattern, separating concerns across clearly defined layers.
Key improvements:

Full migration from Java to Kotlin with idiomatic language features (null safety, coroutines, data classes)
MVVM architecture with dedicated ViewModel and ViewModelFactory classes for each screen (Login, Dashboard, Goal Weight, Weight History)
Repository pattern (WeightRepository) to abstract data access from the UI layer
SecurityUtils utility for password hashing and input validation
SecureSessionManager for encrypted session handling using Android's EncryptedSharedPreferences
Custom registration dialog with input validation
Unit tests for entities, security utilities, and goal weight logic

Enhancement Two – Algorithms and Data Structures
Milestone 3 | Focus: Statistical analysis, caching, and analytics
New algorithmic components were introduced to provide users with meaningful insights into their weight data, along with performance-optimized data structures.
Key improvements:

WeightStatistics algorithm class implementing calculations for average weight, standard deviation, rate of change, trend detection, and projected goal date estimation
WeightHistoryCache using an LRU (Least Recently Used) caching strategy to reduce redundant database queries and improve performance
New Analytics screen (AnalyticsActivity / AnalyticsViewModel) presenting computed statistics to the user
Unit tests for statistical calculations and cache behavior (WeightStatisticsTest, WeightHistoryCacheTest)

Enhancement Three – Databases
Milestone 4 | Focus: Cloud database integration and RESTful API
A Node.js/Express backend was built to connect the application to a MongoDB Atlas cloud database, replacing the local-only SQLite storage with a scalable, cloud-hosted solution.
Backend stack:

Runtime: Node.js with Express 5
Database: MongoDB Atlas (Mongoose ODM)
Authentication: JWT (JSON Web Tokens) with bcrypt password hashing
Architecture: RESTful API with modular route files

API endpoints:
MethodEndpointDescriptionPOST/api/auth/registerRegister a new userPOST/api/auth/loginAuthenticate and receive JWTGET/api/weightsRetrieve weight entries (auth required)POST/api/weightsAdd a weight entry (auth required)DELETE/api/weights/:idDelete a weight entry (auth required)GET/api/statsRetrieve weight statistics (auth required)
Backend models: User, WeightEntry, GoalWeight (Mongoose schemas)

Repository Structure
├── CS360_Project/                  # Original artifact (Java, CS 360)
│   └── WeightTrackingApp/
├── Milestone 2/                    # Enhancement 1: Software Design & Engineering
│   ├── EnhancedWeightTrackingApp/  # Kotlin + MVVM rewrite
│   └── CS499 Milestone 2 Narrative.docx
├── Milestone 3/                    # Enhancement 2: Algorithms & Data Structures
│   ├── EnhancedWeightTrackingApp/  # + Analytics, statistics, caching
│   └── Milestone Three Narrative.docx
├── Milestone 4/                    # Enhancement 3: Databases
│   ├── EnhancedWeightTrackingApp/  # Final Android app
│   ├── weight-tracker-backend/     # Node.js + MongoDB Atlas backend
│   └── Milestone Four Narrative.docx
└── README.md

Getting Started
Android App (Enhanced)
Prerequisites: Android Studio Hedgehog or later, Android SDK 34+

Open the EnhancedWeightTrackingApp folder from the desired milestone in Android Studio.
Sync Gradle dependencies.
Run on an emulator or connected device (minimum API 26).

Backend API (Milestone 4)
Prerequisites: Node.js 18+, MongoDB Atlas account

Navigate to the weight-tracker-backend directory.
Create a .env file with your MongoDB connection string and JWT secret:

   MONGODB_URI=your_mongodb_atlas_connection_string
   JWT_SECRET=your_jwt_secret
   PORT=3000

Install dependencies and start the server:

bash   npm install
   node index.js


This ePortfolio addresses all five CS 499 course outcomes:

Collaborative Environments — Code review video walkthrough, in-code documentation, and contextual comments throughout all enhancements.
Professional Communication — Written narratives for each milestone, professional self-assessment, and clear technical documentation.
Algorithmic Problem Solving — Statistical analysis algorithms, LRU caching, and trend computation demonstrating design trade-offs.
Innovative Techniques and Tools — Kotlin migration, MVVM architecture, encrypted session management, and cloud database integration.
Security Mindset — Input validation, password hashing (bcrypt), JWT authentication, encrypted shared preferences, and secure session handling.

Code Review
The informal code review video walks through the original artifact's functionality, identifies areas for improvement, and outlines the planned enhancements across all three categories. It is available in the ePortfolio.
Watch on https://www.youtube.com/watch?v=i_Of2lJ54Qg

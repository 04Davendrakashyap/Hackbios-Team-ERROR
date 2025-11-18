
# MediSync Pro: A Modern Hospital Management System

**MediSync Pro** is a comprehensive, AI-enhanced web application designed to streamline hospital operations and improve patient care. It provides a seamless, integrated platform for both hospital administrators and patients, featuring a dual-portal system with role-specific functionalities.

---

## 🚀 Key Features

The application is divided into two main portals: a secure **Admin Dashboard** for hospital staff and a user-friendly **Public Portal** for patients.

### 🏥 Hospital Admin Portal (`/dashboard`)

A centralized command center for managing all hospital operations.

*   **Real-time Dashboard:** Get an at-a-glance overview of key metrics, including patient count, bed availability, and pending appointments.
*   **Bed Management:** A visual, color-coded grid to monitor and manage bed occupancy (ICU, General, Emergency) in real-time. Staff can assign and release beds with ease.
*   **Doctor & Patient Management:** Maintain comprehensive directories for doctors and patients, including profiles, schedules, and medical records.
*   **Appointment System:** A complete system to schedule, approve, and reject patient appointments.
*   **Emergency Transfers:** Securely initiate and manage the transfer of patients to other hospitals, sharing critical medical data instantly.
*   **Billing Module:** Generate and track patient invoices, with summaries of total revenue and outstanding payments.

### ❤️ Public Patient Portal (`/public-portal`)

An accessible and intuitive portal for patients to manage their healthcare journey.

*   **Hospital & Doctor Search:** A powerful search engine to find hospitals or specific doctors by name, location, or specialization.
*   **AI Symptom Checker:** An intelligent, Genkit-powered tool that provides a preliminary analysis of symptoms, suggests potential conditions, and offers recommendations.
*   **Online Appointment Booking:** Patients can view doctors' available slots and book appointments directly through the portal.
*   **Emergency Declaration:** A one-click feature to send an emergency alert to a selected hospital, ensuring rapid response.
*   **Unified Patient Profile:** Patients can manage their personal information and view a consolidated medical history, including self-reported records.

---

## 🛠️ Technology Stack

MediSync Pro is built on a modern, robust, and scalable technology stack.

*   **Frontend:**
    *   **Next.js & React:** For building a fast, server-rendered user interface with the App Router.
    *   **TypeScript:** For type safety and improved code quality.
*   **Styling:**
    *   **Tailwind CSS:** A utility-first CSS framework for rapid UI development.
    *   **ShadCN UI:** A collection of beautifully designed, accessible, and reusable components.
*   **Backend & Database:**
    *   **Firebase:** Used as the primary backend-as-a-service.
        *   **Firestore:** A NoSQL database for storing all application data, including patient records, appointments, and hospital details.
        *   **Firebase Authentication:** Securely manages user authentication for both hospital admins and patients.
        *   **Firebase Security Rules:** Enforces granular, path-based access control to protect sensitive data.
*   **Generative AI:**
    *   **Google Genkit (Gemini Pro):** Powers the AI Symptom Checker, providing intelligent analysis and structured JSON output.

---

## 🏛️ System Architecture

The application is designed with a client-centric architecture, leveraging the power of Firebase for backend services.

*   **Data Model:** Firestore is structured with top-level collections for `hospitals` and `users` (patients). Sub-collections within each hospital (e.g., `/hospitals/{id}/patients`, `/hospitals/{id}/doctors`) ensure data segregation and allow for scalable, path-based security rules. A root-level `transfer_history` collection manages data for inter-hospital patient transfers.
*   **Real-time Updates:** The UI is built with custom React hooks (`useCollection`, `useDoc`) that subscribe to Firestore in real-time, ensuring the dashboard and other components are always up-to-date.
*   **Security:** Access control is managed entirely by **Firebase Security Rules**. The rules are designed to be path-aware, ensuring that a hospital admin can only access data within their own hospital's collections and patients can only access their own profiles. This serverless security model is both robust and efficient.

This structured approach creates a powerful, scalable, and secure platform for modern healthcare management.

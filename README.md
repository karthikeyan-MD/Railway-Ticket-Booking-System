# Railway Ticket Booking System

A console-based Java application designed to simulate a railway reservation system. The system manages passenger bookings, berth allocations, and handles overflows using RAC (Reservation Against Cancellation) and Waiting List queues.

## 🚀 Features

*   **Ticket Booking:** Book tickets by providing name, age, gender, and berth preference (Lower, Middle, Upper).
*   **Smart Allocation:** 
    *   Prioritises **Lower (L)** berths for passengers over age 60 or female passengers.
    *   Automatically manages **Confirmed**, **RAC**, and **Waiting List** statuses based on availability.
*   **Management:**
    *   View confirmed, RAC, and waiting list tickets separately.
    *   Check current available berths.
    *   Cancel existing bookings (logic handled by `TicketSystem`).

## 🛠️ System Components

The project consists of three primary Java classes:

1.  **`Passenger.java`**: A model class that stores passenger details, including their unique Ticket ID and allotted berth.
2.  **`TicketSystem.java`**: The core engine that manages the booking logic, berth availability, and the queues for RAC and Waiting Lists.
3.  **`TicketBooking.java`**: The entry point of the application containing the command-line interface and the main menu.

## 📋 Prerequisites

*   **Java Development Kit (JDK)** 8 or higher installed on your system.
*   A terminal or command prompt.

## 🏃 How to Run

1.  **Clone or Download** the source files (`Passenger.java`, `TicketSystem.java`, `TicketBooking.java`) into a single directory.
2.  **Open your terminal** and navigate to that directory.
3.  **Compile the source files** using the following command:
    ```bash
    javac Passenger.java TicketSystem.java TicketBooking.java
    ```
4.  **Run the application**:
    ```bash
    java TicketBooking
    ```

## 🎮 How to Use

Once the application is running, you will be presented with a menu:
1.  **Book Ticket**: Enter passenger details. The system will first try to fill confirmed berths, then RAC (1 spot), then the Waiting List (1 spot).
2.  **Cancel Ticket**: Provide the ticket details to remove a booking and shift passengers up from RAC/Waiting List.
3.  **View Status**: Options 3–6 allow you to see exactly who is booked and what berths are still free.
4.  **Exit**: Close the application.

## ⚙️ Allocation Logic (Internal)
*   **Confirmed Berths**: Initial available berths are "L" (Lower), "U" (Upper), and "M" (Middle).
*   **RAC**: If all berths are full, the next passenger is moved to the RAC queue (Limit: 1).
*   **Waiting List**: If RAC is full, the passenger is moved to the Waiting List (Limit: 1).

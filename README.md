# Light UPS

**Light UPS** is a lightweight, high-performance UPS management solution built with **Qt 6.9 (C++)**. This project provides a reliable, resource-efficient alternative to proprietary UPS software, specifically designed to eliminate connectivity issues, excessive disk wear, and cumbersome browser-based interfaces.

## 💡 The Motivation
The idea for this project emerged after using an **NHS Mini Senoidal UPS**. The manufacturer's original software had several critical flaws that compromised system safety:
* **Silent Connection Failures:** The software often failed to detect the UPS upon system startup without notifying the user, meaning automatic shutdowns would not trigger when needed.
* **SSD Wear:** The service constantly wrote log files to the disk, which is suboptimal for SSD longevity.
* **Inconvenient UX:** Status monitoring and settings were handled via a local web server (localhost) in a browser, rather than a native application.

## 🚀 The Solution
Light UPS solves these issues by providing a native C++ application that is both "light" on resources and heavy on reliability:

* **System Tray Integration:** A dedicated status icon in the tray provides immediate feedback.
* **Native GUI:** A compact menu and window for changing configurations and viewing a real-time log of UPS messages.
* **Zero-Disk Logging:** The application does not write to the hard drive/SSD. Limited, essential log messages are sent directly to the **Windows Event Viewer**.
* **Plugin-Based Architecture:** The software uses a modular driver system. This makes it easy to extend support for other UPS brands and models by simply adding a new plugin.

## 🛠 Technical Stack
* **Language:** C++
* **Framework:** Qt 6.9
* **Platform:** Windows (utilizing Windows Event Viewer for system logs)
* **Architecture:** Plugin-driven driver system

## 📅 Roadmap: Hardware Integration
The next phase of this project is the development of a **low-budget embedded controller**. 

Currently, most UPS setups require one PC to act as a "host" via USB. My solution will move the intelligence to an external controller that can inform up to **4 PCs** about the UPS and mains power status simultaneously. This removes the "single point of failure" host dependency. A dedicated plugin will be created to interface with this controller.

## 📦 Installation
The project uses a **QInstaller** based setup. The installer handles the environment configuration through a structured wizard (Introduction, Component Selection, etc.) to ensure the service and tray application are correctly registered on your system.

---

*Developed by the Light UPS Organisation.*

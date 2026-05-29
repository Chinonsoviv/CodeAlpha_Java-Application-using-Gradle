# Automated Java Application with Gradle and GitHub Actions CI/CD

This repository demonstrates an automated, enterprise-ready Java development workflow utilizing the core principles of DevOps. It implements structural build automation, explicit dependency tracking, and a continuous integration pipeline to ensure cross-platform reproducibility.

## 📊 Project Objectives & Solutions Covered

*   **Task 1: Build Automation (Gradle)** ── Eliminated manual IDE compilation scripts by structuring a standardized build lifecycle managed entirely through the Gradle build engine.
*   **Task 2: Efficient Dependency Management** ── Declared and locked external dependencies directly within configuration scripts, utilizing secure retrieval channels from the Maven Central repository.
*   **Task 3 & 4: Integrated CI/CD Pipeline** ── Built an automated integration workflow using GitHub Actions to automatically fetch, compile, and verify source files on a cloud-hosted runner.
*   **Task 5: DevOps Core Architecture** ── Overcame cross-platform infrastructure hurdles (Windows execution to Linux runtime permission mapping) to achieve full build idempotency.

---

## 🛠️ Technology Stack & Environment

*   **Language:** Java (OpenJDK 21)
*   **Build Automation Tool:** Gradle 9.5.1 (Kotlin DSL configuration script)
*   **Dependency Engine:** Maven Central Repository
*   **CI/CD Infrastructure:** GitHub Actions (Hosted Ubuntu/Linux Server)
*   **Local Package Manager:** Scoop (Environment isolation)

---

## 📦 System Architecture & Directory Layout

The project utilizes a modular infrastructure pattern to isolate system settings from source compilation targets:

├── .github/
│   └── workflows/
│       └── ci.yml             # Cloud Pipeline Configuration Script
├── app/
│   ├── src/
│   │   ├── main/java/         # Application Source Files
│   │   └── test/java/         # Automated Unit Test Suites
│   └── build.gradle.kts       # Centralized Dependency and Plugin File
├── gradlew                    # Unix/Linux Executable Bootstrapper
├── gradlew.bat                # Windows Console Bootstrapper
└── settings.gradle.kts        # Root Project Namespace Declaration

---

## 🚀 Local Deployment Execution

To run and execute this codebase locally on any host operating system without pre-installing comprehensive build tools:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com
   cd CodeAlpha_Java-Application-using-Gradle
   ```

2. **Execute Local Build & Application Lifecycle:**
   ```bash
   # Windows PowerShell / Command Prompt
   ./gradlew run

   # Linux / macOS Terminals
   chmod +x gradlew
   ./gradlew run
   ```

---

## 🏗️ Automated CI/CD Pipeline Lifecycle

The continuous integration logic inside `.github/workflows/ci.yml` triggers automatically on every single `git push` or `pull_request` event. The cloud worker performs the following tasks:

1. **Virtualization:** Provisions a clean `ubuntu-latest` Linux environment.
2. **Checkout:** Clones the source repository dynamically into the host container.
3. **Environment Setup:** Installs and configures an identical instance of OpenJDK 21.
4. **Caching:** Caches build configurations to shorten network processing loops.
5. **Quality Verification:** Executes `./gradlew build` to compile the app and trigger unit tests. A green status badge confirms the current codebase is production-stable.

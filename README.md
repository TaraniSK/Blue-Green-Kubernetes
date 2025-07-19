
# 🌐 Orgpulse – Blue-Green Deployment using Kubernetes

**Orgpulse** is a PHP-MySQL web application deployed using a **Blue-Green Deployment** strategy on **Kubernetes**. This project demonstrates how to achieve **zero-downtime updates**, **safe rollbacks**, and **seamless user experience** during production releases by managing two parallel environments.

---

## 📘 What is Blue-Green Deployment?

**Blue-Green Deployment** is a release management strategy that involves running **two identical environments**:

- **Blue Environment**: The current stable/live version of the application.
- **Green Environment**: The new version to be released.

At any time, only one of them is actively receiving traffic. Switching from one to another is done by simply changing the **service routing**, which leads to:

- 🟢 Minimal or zero downtime  
- 🔁 Quick rollback capability  
- 🧪 Parallel validation of the new release  

---

## 🏗 Project Overview

The Orgpulse project simulates a production-grade blue-green deployment scenario using:

- **Kubernetes (Minikube)**: As the container orchestration platform.
- **PHP + MySQL**: Web application stack.
- **phpMyAdmin (optional)**: For database inspection.
- **YAML Configs**: Separate manifests for blue and green deployments.

---

## 🧱 System Architecture

         +------------------------+
         |    Kubernetes Cluster  |
         +------------------------+
          |            |
    +-----+-----+  +---+-----+
    | Blue Pods |  | Green Pods |   <- Application Versions
    +-----+-----+  +---+-----+
          |            |
         +-------------+
         |   Service   |   <- Routes traffic to either Blue or Green
         +-------------+
                |
            End Users
```

## ✅ Key Concepts Demonstrated

### 🔄 Zero Downtime Deployment
The switch between blue and green is done by changing the Kubernetes service selector, resulting in no application downtime for end users.

### 🧯 Safe Rollback
If a bug or issue is found in the new version (green), the service can quickly be switched back to the blue version without any re-deployment or restart.

### 🧩 Component Isolation
Code changes are introduced only in the green environment. The blue environment remains untouched, allowing safer testing in production.

### 💾 Shared Database
Despite switching application versions, the backend MySQL database remains consistent and persistent. This ensures all user data and application state is preserved.

### 🧪 Visual Cues
The green version of Orgpulse contains visible styling or logo changes, allowing developers and testers to confirm the correct version is live.

---

## ⚙️ Technologies Used

- **PHP** – Server-side scripting for the web app  
- **MySQL** – Backend database for user and application data  
- **Kubernetes (Minikube)** – Container orchestration platform  
- **phpMyAdmin (optional)** – GUI for database interaction  
- **YAML** – Kubernetes manifest language for resource definitions  

---

## 📝 Conclusion

Blue-Green Deployment is a powerful pattern for **high-availability systems** where downtime is unacceptable. With Kubernetes, it becomes easier to implement and manage such deployment workflows in a clean, declarative, and automated fashion.

Orgpulse demonstrates this strategy in action, serving as a foundation for scalable and production-grade web deployments.


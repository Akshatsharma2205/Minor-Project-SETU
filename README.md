# 🌉 सेतु SETU — Citizen Grievance Redressal Portal

<p align="center">
  <img src="https://res.cloudinary.com/dn6hkqmrt/image/upload/v1763748052/SETU_LOGO-removebg_kxwnmb.png" alt="Setu Logo" width="120">
</p>

<p align="center">
  <strong>Your Voice, Our Action.</strong><br>
  A unified platform for citizens to register grievances and track resolutions with transparency and accountability.
</p>

<p align="center">
  <a href="https://ionstack.site">🌐 Live Demo</a> •
  <a href="#features">✨ Features</a> •
  <a href="#tech-stack">🛠️ Tech Stack</a> •
  <a href="#getting-started">🚀 Getting Started</a>
</p>

---

## 📖 About

**Setu** (meaning "Bridge" in Hindi) is a full-stack Citizen Grievance Redressal Portal that bridges the gap between citizens and government departments. Citizens can submit complaints with photo evidence and GPS location, track resolution status in real-time, and earn civic points for participation. Government officials manage grievances through role-based dashboards.

---

## ✨ Features

### 🧑‍💻 Citizen Portal
- **Register & Login** — Email/password with OTP verification + Google OAuth sign-in
- **Submit Grievances** — File complaints with category selection, photo attachments, and GPS location
- **Real-time Tracking** — Track grievance status from submission to resolution
- **Civic Points** — Earn reward points for submitting reports and providing feedback
- **Profile Management** — Update personal details, view history
- **Feedback System** — Rate the resolution quality after closure

### 🏛️ Government Dashboard (Role-Based Access)
- **Worker** — View assigned grievances, update status
- **Operator** — Manage and assign grievances within department
- **Department Admin** — Oversee department-level operations, add users
- **Super Admin** — Full system control, manage departments, view analytics

### 🗺️ Live Grievance Map
- Interactive map powered by **Leaflet.js** showing grievance locations across India
- Color-coded markers by status (New, Under Review, Resolved, Closed)

### 🌐 Multi-Language Support
- Available in **10 Indian languages** including Hindi, Marathi, Tamil, Telugu, Bengali, and more

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Backend** | Java Servlets & JSP (Jakarta EE 6.0) |
| **Database** | MySQL with HikariCP connection pooling |
| **Authentication** | BCrypt password hashing + Google OAuth 2.0 |
| **Email Service** | SendGrid API |
| **Image Storage** | Cloudinary |
| **Frontend** | HTML, Tailwind CSS, JavaScript |
| **Maps** | Leaflet.js |
| **Animations** | ScrollReveal.js |
| **Build Tool** | Maven |
| **Deployment** | Docker + Jetty 11 |
| **Analytics** | Google Analytics |

---

## 🚀 Getting Started

### Prerequisites
- Java 11+
- Maven 3.8+
- MySQL database
- Docker (optional, for containerized deployment)

### Environment Variables

Create a `.env` file or set these environment variables on your server:

| Variable | Description |
|----------|-------------|
| `DB_URL` | MySQL JDBC connection URL |
| `DB_USER` | Database username |
| `DB_PASSWORD` | Database password |
| `CLIENT_ID` | Google OAuth 2.0 Client ID |
| `CLIENT_SECRET` | Google OAuth 2.0 Client Secret |
| `EMAIL_API` | SendGrid API key |
| `SENDER_EMAIL` | Sender email address for OTP/notifications |
| `CLOUD_NAME` | Cloudinary cloud name |
| `api_key` | Cloudinary API key |
| `api_secret` | Cloudinary API secret |

### Run Locally

```bash
# Clone the repository
git clone https://github.com/Akshatsharma2205/Minor-Project-SETU.git
cd Minor-Project-SETU

# Build with Maven
mvn clean package

# Deploy the generated .war file to a Jetty/Tomcat server
```

### Run with Docker

```bash
# Build the Docker image
docker build -t setu-portal .

# Run the container with environment variables
docker run -p 8080:8080 \
  -e DB_URL=your_db_url \
  -e DB_USER=your_db_user \
  -e DB_PASSWORD=your_db_password \
  -e CLIENT_ID=your_google_client_id \
  -e CLIENT_SECRET=your_google_client_secret \
  -e EMAIL_API=your_sendgrid_key \
  -e SENDER_EMAIL=your_sender_email \
  -e CLOUD_NAME=your_cloudinary_name \
  -e api_key=your_cloudinary_key \
  -e api_secret=your_cloudinary_secret \
  setu-portal
```

---

## 📁 Project Structure

```
Minor-Project-SETU/
├── src/main/java/
│   ├── controller/          # Servlets (Login, Registration, Grievance, OAuth)
│   ├── model/
│   │   ├── dao/             # Data Access Objects (CitizenDAO, GovDAO, ReportDAO)
│   │   ├── entity/          # Entity classes (Citizen, GovUser, Report)
│   │   ├── Database.java    # HikariCP connection pool
│   │   └── EmailUtil.java   # SendGrid email utility
├── src/main/webapp/
│   ├── citizen/             # Citizen-facing JSP pages
│   ├── gov/                 # Government dashboard JSP pages
│   ├── js/                  # JavaScript files
│   ├── style/               # CSS stylesheets
│   └── index.html           # Landing page
├── Dockerfile               # Multi-stage Docker build
├── pom.xml                  # Maven dependencies
└── .gitignore
```

---

## 👥 Team

Designed, Developed and Hosted by **Team SETU**

---

## 📄 License

This project is open source and available for educational purposes.

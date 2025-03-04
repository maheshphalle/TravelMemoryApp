# TravelMemory MERN Stack Deployment on AWS

## 📌 Project Overview
TravelMemory is a full-stack MERN (MongoDB, Express, React, Node.js) application deployed on AWS EC2. This project demonstrates the complete setup of a **scalable** and **secure** cloud-hosted application with **Nginx, Load Balancer, and Cloudflare DNS configuration**.

## 🏗 Deployment Architecture

![Deployment Diagram](deployment_diagram.png)

## 🚀 Features
- **Frontend:** React application served via Nginx on EC2.
- **Backend:** Node.js with Express, using Nginx as a reverse proxy.
- **Database:** MongoDB hosted on MongoDB Atlas.
- **Load Balancer:** AWS Application Load Balancer distributing traffic.
- **Custom Domain:** Configured via Cloudflare.
- **Scalability:** Deployed using AWS AMIs for quick instance replication.

## ⚙️ Technologies Used
- **Frontend:** React, Nginx
- **Backend:** Node.js, Express.js, Nginx
- **Database:** MongoDB (Atlas)
- **Cloud Services:** AWS EC2, Load Balancer, Cloudflare
- **CI/CD:** Git & GitHub

## 📖 Deployment Steps

### 1️⃣ **Set Up EC2 Instances**
- Create two EC2 instances (Frontend & Backend) using Ubuntu 22.04 LTS.
- Configure security groups to allow SSH, HTTP, and API ports.

### 2️⃣ **Clone the Project**
```bash
# On both frontend and backend EC2 instances
cd ~
git clone https://github.com/maheshphalle/TravelMemoryApp.git
```

### 3️⃣ **Set Up Backend**
```bash
cd TravelMemoryApp/backend
npm install
nano .env  # Add MongoDB connection string
node server.js  # Run the backend
```

### 4️⃣ **Set Up Frontend**
```bash
cd TravelMemoryApp/frontend
npm install
nano src/config/urls.js  # Update backend API URL
npm run build
```

### 5️⃣ **Configure Nginx**
```bash
sudo apt install -y nginx
sudo nano /etc/nginx/sites-available/default  # Add reverse proxy config
sudo systemctl restart nginx
```

### 6️⃣ **Create AWS AMIs & Launch Scalable Instances**
- Create Amazon Machine Images (AMIs) after testing.
- Launch new instances from AMIs.

### 7️⃣ **Configure Load Balancer & Cloudflare**
- Create AWS Target Groups (Frontend & Backend).
- Attach EC2 instances to the Load Balancer.
- Map a custom domain using Cloudflare DNS settings.

## 🖥 Access the Application
- **Frontend:** `http://your-domain.com`
- **Backend API:** `http://your-domain.com/api/`

## 📸 Screenshots & Documentation
Include **screenshots of AWS setup, Cloudflare settings, and GitHub repo structure**.

## 📝 Contributing
Feel free to contribute by forking the repo and submitting a pull request.

## 🔗 Contact
- **Author:** Mahesh Phalle
- **Email:** mahesh.phalle@outlook.com
- **GitHub:** [maheshphalle](https://github.com/maheshphalle)

---

### 🎯 **Project Status: Completed ✅**
This project is successfully deployed and accessible online.

---

# Travel Memory

`.env` file to work with the backend after creating a database in MongoDB: 

```
MONGO_URI='ENTER_YOUR_URL'
PORT=3001
```

### Data format to be added:
```json
{
    "tripName": "Incredible India",
    "startDateOfJourney": "19-03-2022",
    "endDateOfJourney": "27-03-2022",
    "nameOfHotels":"Hotel Namaste, Backpackers Club",
    "placesVisited":"Delhi, Kolkata, Chennai, Mumbai",
    "totalCost": 800000,
    "tripType": "leisure",
    "experience": "Lorem Ipsum, Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum,Lorem Ipsum, ",
    "image": "https://t3.ftcdn.net/jpg/03/04/85/26/360_F_304852693_nSOn9KvUgafgvZ6wM0CNaULYUa7xXBkA.jpg",
    "shortDescription":"India is a wonderful country with rich culture and good people.",
    "featured": true
}
```

### `.env` File for Frontend
For frontend, create a `.env` file and put the following content (update based on your setup):
```bash
REACT_APP_BACKEND_URL=http://localhost:3001
```

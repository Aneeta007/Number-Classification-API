
 Number Classification API

Overview
This is a FastAPI-based web service that classifies numbers based on various mathematical properties. The API determines whether a number is prime, perfect, Armstrong, odd, or even, and provides a fun fact sourced from the Numbers API.

📡 Deployment
This API is deployed on an **AWS EC2 instance** and is publicly accessible.

---

Features
- Accepts **GET** requests with a `number` parameter
- Returns JSON responses in the specified format
- Handles CORS (Cross-Origin Resource Sharing)
- Provides appropriate HTTP status codes
- Ensures fast response time (< 500ms)

---

Technology Stack
- **Python** (FastAPI)
- **Uvicorn** (ASGI Server)
- **Requests** (For fetching fun facts)
- **AWS EC2** (Deployment)
- **Git & GitHub** (Version Control)

---

API Specification
Endpoint:**
`GET /api/classify-number?number=<integer>`

### **✅ Successful Response (200 OK):**
```json
{
    "number": 371,
    "is_prime": false,
    "is_perfect": false,
    "properties": ["armstrong", "odd"],
    "digit_sum": 11,
    "fun_fact": "371 is an Armstrong number because 3^3 + 7^3 + 1^3 = 371"
}
```

### **❌ Error Response (400 Bad Request):**
```json
{
    "number": "invalid_input",
    "error": true
}
```

---

## 🚀 Setup & Installation
### **1️⃣ Clone the Repository**
```bash
git clone https://github.com/YOUR_GITHUB_USERNAME/number-api.git
cd number-api
```

### **2️⃣ Create a Virtual Environment & Install Dependencies**
```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### **3️⃣ Run the API**
```bash
uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```

### **4️⃣ Test the API**
Use `curl` or Postman:
```bash
curl "http://127.0.0.1:8000/api/classify-number?number=371"
```

---

## 🖥️ Deploying on AWS EC2
1. **Launch an EC2 instance** with Ubuntu and open port **8000** in Security Groups.
2. **Connect via SSH:**
   ```bash
   ssh -i "your-key.pem" ubuntu@your-ec2-ip
   ```
3. **Install Python & Dependencies:**
   ```bash
   sudo apt update && sudo apt install python3 python3-pip -y
   ```
4. **Run the API in the background:**
   ```bash
   nohup uvicorn main:app --host 0.0.0.0 --port 8000 &
   ```

---

## 🔗 Public URL
Access your API at:
```
http://<your-ec2-ip>:8000/api/classify-number?number=371
```


Happy Coding! 🚀


# Weather Data Collection System Using AWS S3 and OpenWeather API

### **Overview**
This project automates the collection of weather data using the OpenWeather API and stores it securely in AWS S3 for analysis and reporting. The system is designed for scalability and can be used for real-time weather tracking or historical data analysis.

---

### **Features**
- Fetches current weather data for a specified location using OpenWeather API.
- Uploads data to an AWS S3 bucket in JSON format.
- Automates data collection using schedulers like `cron` or AWS Lambda.
- Scalable and easy to integrate with data visualization tools.

---

### **Getting Started**
Follow the steps below to set up and run the system:

#### **Prerequisites**
1. Python 3.8 or later
2. AWS Account with an S3 bucket created
3. OpenWeather API Key
4. Installed Python libraries: `requests`, `boto3`

#### **Installation**
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/weather-data-collection.git
   cd weather-data-collection
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Configure your environment variables for AWS credentials and OpenWeather API key:
   ```bash
   export AWS_ACCESS_KEY_ID="your_aws_access_key"
   export AWS_SECRET_ACCESS_KEY="your_aws_secret_key"
   export OPENWEATHER_API_KEY="your_openweather_api_key"
   ```

---

### **Usage**
#### **1. Fetch Weather Data**
Run the Python script to fetch weather data:
```bash
python fetch_weather.py
```

#### **2. Upload Data to S3**
Upload the fetched data to AWS S3:
```bash
python upload_to_s3.py
```

#### **3. Automate Data Collection**
Set up a `cron` job or use AWS Lambda to schedule data collection.

Example `cron` setup:
```bash
0 * * * * python /path/to/fetch_weather.py && python /path/to/upload_to_s3.py
```

---

### **Project Structure**
```
weather-data-collection/
├── fetch_weather.py      # Script to fetch weather data from OpenWeather API
├── upload_to_s3.py       # Script to upload data to AWS S3
├── requirements.txt      # Dependencies
├── README.md             # Documentation
└── data/                 # (Optional) Local storage for testing
```

---

### **API Reference**
- **OpenWeather API**: [Documentation](https://openweathermap.org/api)
  - **Endpoint**: `http://api.openweathermap.org/data/2.5/weather`
  - **Parameters**:
    - `q`: City name (e.g., `London`)
    - `appid`: Your API key
    - `units`: Measurement units (`metric` or `imperial`)

---

### **Sample Output**
A sample JSON response from the OpenWeather API:
```json
{
  "coord": { "lon": -0.13, "lat": 51.51 },
  "weather": [{ "description": "light rain", "icon": "10d" }],
  "main": { "temp": 15.23, "humidity": 81 },
  "name": "London"
}
```

Uploaded to S3 as:
```json
{
  "city": "London",
  "timestamp": "2025-01-07T14:00:00Z",
  "temperature": 15.23,
  "humidity": 81,
  "description": "light rain"
}
```

---

### **Potential Enhancements**
- Add a visualization dashboard using Tableau or Python's `matplotlib`.
- Extend to collect weather forecasts or historical data.
- Integrate with AWS Glue for data transformation and AWS Athena for querying.

---

### **License**
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

### **Contributing**
Contributions are welcome! If you'd like to enhance this project, please follow these steps:
1. Fork the repository.
2. Create a feature branch: `git checkout -b feature-new-feature`.
3. Commit changes: `git commit -m 'Add new feature'`.
4. Push to the branch: `git push origin feature-new-feature`.
5. Submit a pull request.

---

### **Contact**
For questions or feedback, feel free to reach out:
- **Author**: Carl Anthony Osborne
- **Email**: app@ehrconsultantforhire.com
- **LinkedIn**: https://www.linkedin.com/in/carlanthonyosborne/  
- **GitHub**: https://github.com/ehrconsultantforhire 

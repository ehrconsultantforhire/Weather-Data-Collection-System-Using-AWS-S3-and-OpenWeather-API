# Weather Data Colection System

In this project we would be building a weather data collection system using AWS S3 and OpenWeather API

# Requirements
- Language: Python 3.x
- Cloud Provider: AWS (S3)
- External API: OpenWeather API
- Dependencies:
    - boto3 (AWS SDK)
    - python-dotenv
    - requests

# Project structure

    weather-dashboard/
    src/
        __init__.py
        weather_dashboard.py
    tests/
    data/
    .env
    .gitignore
    requirements.txt

# Setup Instructions
1. Clone the repository:

    git clone `https://github.com/ehrconsultantforhire/Weather-Data-Collection-System-Using-AWS-S3-and-OpenWeather-API.git`

2. Create and activate a virtual environment for the application (venv)

- Install the python3-venv package
`sudo apt install python3.12-venv`

- Create the virtual environment.
`python3 -m venv venv`

- Activate the virtual environment
`source venv/bin/active`

- Add venv to .gitignore 
`echo "venv/" >> .gitignore`

2. Install dependencies
    `pip install -r requirements.txt`

3. Configure environment variables (.env):

    ```
    OPENWEATHER_API_KEY=your_api_key
    AWS_BUCKET_NAME=your_bucket_name
    ```

4. Configure AWS credentials:

    `aws configure`

5. Run the application

    `python src/weather_dashboard.py`
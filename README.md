# n8n_Daily_Weather_Email_Automation

## Project Overview
This project automates the process of retrieving daily weather information and sending it via email using n8n, OpenWeather API, Supabase and SendGrid SMTP.
The workflow fetches live weather data, formats it into a readable message, and delivers it automatically to the configured email recipient.

## 1. API Setup & Key Configuration
1. OpenWeather API
- Create an account at: https://openweathermap.org
- Generate an API key from the dashboard.
In the n8n HTTP Request node: Method: GET, URL: openweather url, Query Parameters: q - City name for which weather data is requested; units - Unit system for temperature (metric = °C); appid - OpenWeather API key   

2. Supabase Configuration
- Create a Supabase project.
- Create a table
- Use the Data API endpoint provided by Supabase.
- Add the following headers in the HTTP request:
apikey: <SUPABASE_API_KEY>; Authorization: Bearer <SUPABASE_API_KEY>; Content-Type: application/json

   
## 3. Email Configuration
1. SMTP Settings
- Email Provider: SendGrid
- SMTP Host: smtp.sendgrid.net
- Port: 587
- Username: apikey
- Password: SendGrid API Key
- Encryption: STARTTLS (enabled)

3. Sender Setup:
- A Single Sender Identity was created in SendGrid.
- The verified sender email is used in the From field in n8n.
- This ensures successful email delivery and avoids spam rejection.

3. Email Flow:
- Weather data is fetched from the API.
- Data is formatted into an HTML email.
- Email is sent through SendGrid to the specified recipient.

## 4. How to Import & Run the Workflow
1. Open n8n
2. click on create workflow
3. In the top corner click on the three dots ...
4. Click on Import from file 
5. Upload the .json file
6. The workflow will open automatically in the editor.
7. Click Save (top-right) and then Activate the workflow.

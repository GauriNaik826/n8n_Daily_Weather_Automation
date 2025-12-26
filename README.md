# n8n_Daily_Weather_Email_Automation

## Project Overview
This project automates the process of retrieving daily weather information and sending it via email using n8n, OpenWeather API, Supabase and SendGrid SMTP.
The workflow fetches live weather data, formats it into a readable message, and delivers it automatically to the configured email recipient.

## 1. API Setup & Key Configuration
1. OpenWeather API
- Create an account at: https://openweathermap.org
- Generate an API key from the dashboard.
In the n8n HTTP Request node: Method: GET, URL: openweather url, Query Parameters: q - City name for which weather data is requested; units - Unit system for temperature (metric = °C); appid - OpenWeather API key   



URL:
1. Openwether API- signup and get the Defualt Api key 
in the http request node, method is GET, URL is the openweather url, in the quey parameters add the q: London , units : etric, appid: API key
2. Supabase Setup - singu p and create a porject ad then table editir create a table called weather log 
method is POST in the URL paste the url found in DATA api /rest/v1/weathe_log
header paremeters - paste the  apikey: APIKEY,  Authorization : Beaeer APIkey , contet type : application/json, Prefer: return=representation, body type add the json bpdy

   
## 3. Email Configuration
First setup the SMPTP configuration 
Email Provider: SendGrid
SMTP Host: smtp.sendgrid.net
Port: 587
Encryption: STARTTLS (enabled)

Authentication :
Username: apikey
Password: SendGrid API Key

Sender Setup:
A Single Sender Identity was created and verified in SendGrid. The verified email address is used as the From Email in n8n.

Email Flow:
n8n connects to SendGrid using SMTP credentials. Emails are sent via SendGrid to the recipient address. The sender email must match the verified sender in SendGrid. send it via HTML 

✅ This setup ensures secure and reliable email delivery using SendGrid’s SMTP service.

## 4. How to Import & Run the Workflow
1. Open n8n
2. click on create workflow
3. In the top corner click on the three dots ...
4. Click on Import from file 
5. Upload the .json file
6. The workflow will open automatically in the editor.
7. Click Save (top-right) and then Activate the workflow.

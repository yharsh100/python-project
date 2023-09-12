# python-project
# Develop a simple automated test script using Python) and a testing framework (e.g., Selenium, Appium) to automate the login process of a sample web application.
from selenium import webdriver
from selenium.webdriver.common.keys import Keys

# Initialize the WebDriver (you should provide the path to your WebDriver)
driver = webdriver.Chrome(executable_path='/path/to/chromedriver')

# Navigate to the login page
driver.get('https://your-sample-website.com/login')

# Find and fill in the username and password fields
username_input = driver.find_element_by_id('username')  # Replace with the actual HTML element ID
password_input = driver.find_element_by_id('password')  # Replace with the actual HTML element ID

username_input.send_keys('your_username')
password_input.send_keys('your_password')

# Submit the form by pressing Enter or clicking the login button
password_input.send_keys(Keys.RETURN)  # You can use Keys.ENTER instead of Keys.RETURN

# Wait for the login to complete (you can add more advanced waiting strategies)
driver.implicitly_wait(10)  # Wait for up to 10 seconds

# Check if the login was successful (you should replace this with your verification logic)
if 'Dashboard' in driver.page_source:
    print('Login successful!')
else:
    print('Login failed.')

# Close the browser window
driver.quit()

# license key for terminal_app (example)

pip install npyscreen

main.py
```
import requests
from module1 import function1
from module2 import function2

def check_license_key(license_key):
    # API EndPoint
    api_url = "https://your-server.com/api/check_license_key"
    response = requests.post(api_url, data={"license_key": license_key})
    
    if response.status_code == 200:
        return response.json()["valid"]
    else:
        return False

entered_license_key = input("Bitte geben Sie Ihren Lizenzschlüssel ein: ")

if check_license_key(entered_license_key):
    print("License key is valid. The application will start.")
    # Starten Sie hier Ihre Anwendung, z. B. durch Aufruf der Hauptfunktion
    function1()
    function2()
else:
    print("Invalid license key. Access denied")
 ```
  
my_app.py
    
    ```    
import npyscreen

class MyApp(npyscreen.NPSAppManaged):
    def onStart(self):
        self.addForm("MAIN", MainForm, name="Welcome to My App")

class MainForm(npyscreen.Form):
    def create(self):
        self.my_name = self.add(npyscreen.TitleText, name="Your Name:")

    def afterEditing(self):
        self.parentApp.setNextForm(None)

if __name__ == "__main__":
    my_app = MyApp()
    my_app.run()
 ```    

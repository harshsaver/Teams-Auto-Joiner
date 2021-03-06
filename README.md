
# Teams-Auto-Joiner  
[![GitHub stars](https://img.shields.io/github/stars/TobiasPankner/Teams-Auto-Joiner.svg?style=social&label=Star)](https://GitHub.com/TobiasPankner/Teams-Auto-Joiner/stargazers/)    


- [Prerequisites](#prerequisites)
-  [Configuration options](#configuration-options)
- [Run the script](#run-the-script)  

Python script to automatically join Microsoft Teams meetings.  
Automatically turns off your microphone and camera before joining. Automatic login and blacklist can be set in the config file.  
  
Always joins the newest meeting and leaves either after a specified time, if you are the last person in the meeting or only if a new one is available (see [Configuration options](#configuration-options) for more information).
  
![Demo](https://imgur.com/VQOJl8w.gif)

## Prerequisites  
  
 - Python3 ([Download](https://www.python.org/downloads/))  
   
## Configuration options  
  
- **email/password:**  
The email/password of your Microsoft account (can be left empty if you don't want to automatically login)  

- **start_automatically:**  
If true, skips the `Start [s], Reload teams [r], Quit [q]` dialog and starts on it's own. Useful if you schedule the script to start at a specific time.  

- **organisation_num:**     
If your Teams account is in multiple organisations, as seen in the example below, change the organisation_num to the number of the list item (counting starts from 1)  
<img width="30%" src="https://imgur.com/CWpK4wk.png">

- **random_delay:**  
If true, adds a random delay (10s-30s) before joining a meeting. Can be useful so the bot seems more "human like".  

- **auto_leave_after_min:**  
If set to a value greater than zero, the bot leaves every meeting after the specified time (in minutes). Useful if you know the length of your meeting, if this is left a the default the bot will stay in the meeting until a new one is available.

- **leave_if_last:**  
If true, leaves the meeting if you are the last person in it.

- **headless:**     
If true, runs Chrome in headless mode (does not open GUI window and runs in background).

- **mute_audio:**     
If true, mutes all the sounds.

- **chrome_type:**     
Valid options: `google-chrome`, `chromium`, `msedge`. By default, google chrome is used, but the script can also be used with Chromium or Microsoft Edge.

- **blacklist:**  
A list of Teams and their channels to ignore. Meetings ocurring in these channels will not be joined.  
If you have a Team called "Test1" and, within that, two channels called "General" and "Channel1" and you don't want to join meetings in the "General" Channel: 
```json
"blacklist": [  
  {  
    "team_name": "Test1",  
    "channel_names": [  
      "General"
    ]  
  }
]
```

## Run the script  
  
 1. Rename the [config.json.example](config.json.example) file to "config.json"  
 2. Edit the "config.json" file to fit your preferences (optional)  
 3. Install dependencies:   ```pip install -r requirements.txt``` 
 4. Run [auto_joiner.py](auto_joiner.py): `python auto_joiner.py`  
 5. After starting, teams might be in Grid view, if this is the case change the view to list    
<img src="https://i.imgur.com/GODoJYf.png?2" width="300" height="245" />

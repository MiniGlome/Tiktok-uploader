![made-with-python](https://img.shields.io/badge/Made%20with-Python3-brightgreen)

<!-- LOGO -->
<br />
<p align="center">
  <img src="https://user-images.githubusercontent.com/54740007/212677385-8f453f16-06fd-41e2-83a6-8a25d5435418.png" alt="Logo" width="80" height="80">

  <h3 align="center">TikTok-Uploader</h3>

  <p align="center">
    Python3 script to upload and schedule TikTok videos
    <br />
    </p>
</p>


## About The Project

This project is a Python3 script that allows you to automatically upload and schedule TikTok videos. With this script, you can automate the process of uploading videos to TikTok, allowing you to save time and focus on creating content.

The script is easy to use and requires minimal setup. Simply provide your TikTok *sessionid* cookie, the video file you wish to upload and the video details, and the script will handle the rest. You can also schedule videos to be uploaded at a specific time, making it easy to plan your content in advance.

## Getting Started
To get started you need to have python3 installed. If it is not the case you can download it here : https://www.python.org/downloads/<br><br>
You will also need your TikTok ***sessionid* cookie**. To get it log in to your TikTok account and on the page https://www.tiktok.com/ press the F12 key on your keyboard then Application > Storage > Cookies and find the value of the *sessionid* cookie. You should have something like this: `7a9f3c5d8f6e4b2a1c9d8e7f6a5b4c3d` <br><br>
*Note that you need a **Business account** in order to use the **schedule feature**, if the option is not available on your computer you can switch to a Business account using the smartphone app.*

### Installation
Make sure you've already git installed. Then you can run the following commands to get the scripts on your computer:
   ```sh
   git clone https://github.com/MiniGlome/Tiktok_uploader.git
   cd Tiktok_uploader
   ```
The script only requires the `requests` module, you can install it with this command:
```sh
pip install -r requirements.txt
```
   
## Usage
### Import in your script
You can copy the file `Tiktok_uploader.py` in your project folder and use it like this:
```python
from Tiktok_uploader import uploadVideo

session_id = "7a9f3c5d8f6e4b2a1c9d8e7f6a5b4c3d"
file = "my_video.mp4"
title = "MY SUPER TITLE"
tags = ["Funny", "Joke", "fyp"]
schedule_time = 1672592400

# Publish the video
uploadVideo(session_id, file, title, tags, verbose=True)
# Schedule the video
uploadVideo(session_id, file, title, tags, schedule_time, verbose=True)
```
- `session_id`: Your TikTok *sessionid* cookie.<br>
- `file`: The path to the video you want to upload.<br>
- `title`: The title of your publication (without hashtags).<br>
- `tags`: The list of hashtags you want to add to your post (without `#` symbol). May be empty list `[]`.<br>
- `schedule_time`: The timestamp (in seconds) at which you want to schedule your video.<br>
**Note that you cannot schedule a video more than 10 days in advance.**

### With the command line
```
usage: Tiktok_uploader.py [-h] -i SESSION_ID -p PATH -t TITLE [--tags [TAGS ...]] [-s SCHEDULE_TIME]

options:
  -h, --help            show this help message and exit
  -i SESSION_ID, --session_id SESSION_ID
                        Tiktok sessionid cookie
  -p PATH, --path PATH  Path to video file
  -t TITLE, --title TITLE
                        Title of the video
  --tags [TAGS ...]     List of hashtags for the video
  -s SCHEDULE_TIME, --schedule_time SCHEDULE_TIME
                        schedule timestamp for video upload
```                        
The `session_id`, `path` and `title` fields are required.
    
#### Example
This command will publish the video `my_video.mp4` as `MY SUPER TITLE #Funny #Joke #fyp`
```sh
python3 Tiktok_uploader.py -i 7a9f3c5d8f6e4b2a1c9d8e7f6a5b4c3d -p my_video.mp4 -t "MY SUPER TITLE" --tags Funny Joke Fyp
```
This command will schedule the video `my_video.mp4` for `01/01/2023 18:00:00` (timestamp 1672592400)
```sh
python3 Tiktok_uploader.py -i 7a9f3c5d8f6e4b2a1c9d8e7f6a5b4c3d -p my_video.mp4 -t "MY SUPER TITLE" --tags Funny Joke Fyp -s 1672592400
```

## Donation
If you want to support my work, you can send 2 or 3 Bitcoins 🙃 to this address: 
```
bc1q4nq8tjuezssy74d5amnrrq6ljvu7hd3l880m7l
```
![bitcoin_address](https://user-images.githubusercontent.com/54740007/169100171-1061c7a0-207e-459b-84de-2d6bb93b0f38.png)

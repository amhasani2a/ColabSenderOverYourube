# ColabSenderOverYourube

# Colab YouTube Uploader UI

A graphical user interface (GUI) script for Google Colab that simplifies uploading videos directly to YouTube.

**Acknowledgment:** This script is a frontend wrapper built upon the open-source project [tokland/youtube-upload](https://github.com/tokland/youtube-upload).

## Features

* **Interactive UI:** Uses `ipywidgets` to eliminate the need for manual command-line execution.
* **Multiple Video Sources:** Supports direct URL downloads (`wget`), Google Drive integration, and local file uploads.
* **Metadata Management:** Form fields for Title, Description, Tags, and Privacy status (Public, Private, Unlisted).
* **Automated Setup:** Silently installs required dependencies (`google-api-python-client`, `oauth2client`, etc.) within the Colab environment.

## Prerequisites

You must obtain YouTube Data API credentials before using this script:

1. Go to the [Google Cloud Console](https://console.cloud.google.com/).
2. Create a new project and enable the **YouTube Data API v3**.
3. Configure the **OAuth consent screen** (ensure you add your YouTube email as a Test User).
4. Create credentials for an **OAuth client ID** (Application type must be **Desktop app**).
5. Download the credentials JSON file.

## Execution Instructions

1. Open a new notebook in [Google Colab](https://colab.research.google.com/).
2. Copy and paste the provided Python script into an empty code cell and execute it.
3. An interactive control panel will appear in the cell output.
4. Click **Upload client_secrets** and select the JSON credentials file downloaded from Google Cloud Platform. The script will automatically rename it to `client_secrets.json`.
5. Select your **Video Source**:
* *Direct Link:* Paste a direct download URL in the Path field.
* *Google Drive:* Click **Mount Google Drive**, grant access, and input the absolute path (e.g., `/content/drive/MyDrive/video.mp4`).
* *Upload Local File:* Select a video file from your local machine.


6. Fill in the video metadata (Title, Description, Tags, Privacy).
7. Click **Start Upload Process**.
8. **Authentication:** On the initial run, an authorization link will be generated in the output. Click the link, sign in with your Google account, allow access, and paste the provided authorization code back into the Colab prompt to finalize the upload.

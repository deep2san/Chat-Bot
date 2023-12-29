# Dropbox AI Chat

Quickly summarize the content and get the information you need in **real-time** from private large unstructured documents in your [Dropbox](https://dropbox.com/). The same tool can be used with [OneDrive](https://onedrive.live.com/login/).

## Demo

See how the tool works:

![Dropbox AI search tool demo](assets/dropbox-ai-search-tool.gif)

As you can see the LLM App enables AI-powered search from multiple unstructured documents like tax information from different countries, and indexes input data in real-time just after you upload files to the cloud storage.

## How to run the tool

There are 3 ways to run the app:

### Run with Conda

For a step-by-step walkthrough in real time (~7 mins) check out the video below:

[![Thumbnail of YouTube walkthrough](assets/yt-thumbnail.png)](https://youtu.be/PbSAYHi5gnM?si=GAi3hYFTiJMO0EQH)

### Run with Docker

1. Create `.env` file in the root directory of the project, copy and paste the below config. Replace the `OPENAI_API_TOKEN` configuration value with your key `{OPENAI_API_KEY}` and replace `DROPBOX_LOCAL_FOLDER_PATH` with a path where Dropbox folder is located `{REPLACE_WITH_DROPBOX_FOLDER_PATH}`. For example, if the current project folder is `DROPBOX-SEARCH-TOOL`, you navigate to the Dropbox path in the home directory: `../Dropbox/documents`. Other properties are optional to change and be default.

```bash
OPENAI_API_TOKEN={OPENAI_API_KEY}
EMBEDDER_LOCATOR=text-embedding-ada-002
EMBEDDING_DIMENSION=1536
MODEL_LOCATOR=gpt-3.5-turbo
MAX_TOKENS=200
TEMPERATURE=0.0
DROPBOX_LOCAL_FOLDER_PATH={REPLACE_WITH_DROPBOX_RELATIVE_PATH}
```

2. From the project root folder, open your terminal and run `docker compose up`.
3. Navigate to `localhost:8501` on your browser when docker installion is successful.

### Run from the source

#### Prerequisites

1. Make sure that [Python](https://www.python.org/downloads/) 3.10 or above installed on your machine.
2. Download and Install [Pip](https://pip.pypa.io/en/stable/installation/) to manage project packages.
3. Create an [OpenAI](https://openai.com/) account and generate a new API Key: To access the OpenAI API, you will need to create an API Key. You can do this by logging into the [OpenAI website](https://openai.com/product) and navigating to the API Key management page.
4. Use your Dropbox/OneDrive account.

Then, follow the easy steps to install and get started using the sample app.

#### Step 1: Clone the repository

This is done with the `git clone` command followed by the URL of the repository:

```bash
git clone https://github.com/pathway-labs/dropbox-ai-chat
```

Next,  navigate to the project folder:

```bash
cd dropbox-ai-chat
```

#### Step 2: Set environment variables

Create `.env` file in the root directory of the project, copy and paste the below config, and replace the `{OPENAI_API_KEY}` configuration value with your key.

```bash
OPENAI_API_TOKEN={OPENAI_API_KEY}
HOST=0.0.0.0
PORT=8080
EMBEDDER_LOCATOR=text-embedding-ada-002
EMBEDDING_DIMENSION=1536
MODEL_LOCATOR=gpt-3.5-turbo
MAX_TOKENS=200
TEMPERATURE=0.0
DROPBOX_LOCAL_FOLDER_PATH="../../../mnt/c/Users/bumur/Dropbox/documents"
```

Replace DROPBOX_LOCAL_FOLDER_PATH with your local Dropbox folder path and optionally, you customize other values.

#### Step 3 (Optional): Create a new virtual environment

Create a new virtual environment in the same folder and activate that environment:

```bash
python -m venv pw-env && source pw-env/bin/activate
```

#### Step 4: Install the app dependencies

Install the required packages:

```bash
pip install --upgrade -r requirements.txt
```

#### Step 5: Run the Pathway API

You start the application by running `main.py`:

```bash
python main.py
```

#### Step 6: Run Streamlit UI

You can run the UI separately by running Streamlit app
`streamlit run ui.py` command. It connects to the Pathway's backend API automatically and you will see the UI frontend is running on your browser.

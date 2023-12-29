# Chat-Bot
About Project: We know that the Holy Book "Bhagavad Geeta" has solution to every problem of our life. I made a AI Chat-Bot who reply the solutions to our given problem/prompt according to the Bhagavad Geeta Book.

Working: I had uploaded the "Bhagavad Geeta as it is" book in my dropbox folder and gave this path in my .env folder. I used docker and openai API key for this chatbot.




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

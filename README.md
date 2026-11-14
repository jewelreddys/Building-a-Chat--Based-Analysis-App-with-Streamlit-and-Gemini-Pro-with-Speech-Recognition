**Employee Data Insights
Chat-Based Data Analysis with Streamlit, Google Gemini Pro & Speech Recognition**
An AI-powered conversational analytics application that helps users explore structured CSV datasets using natural-language questions, data-wrangling commands, visualizations, and voice input.
Project context: Developed as an academic project at Vellore Institute of Technology (VIT), with the project report titled Employee Data Insights: Building a Chat-Based Analysis App with Streamlit and Gemini Pro with Speech Recognition.

**Overview**
Exploring structured datasets often requires familiarity with programming, SQL, or business-intelligence tools. This project explores a more accessible workflow: users upload a CSV file and interact with their data through a conversational interface.

The application combines Streamlit for the user interface, Python-based data processing, and Google Gemini Pro for natural-language understanding and response generation. It is designed to return textual insights and visual outputs, while also supporting voice-based queries and natural-language data-wrangling interactions.
**Key capabilities**
The project report describes the following capabilities. The implementation details should be checked against the current source code before treating every item as production-ready.
- CSV upload: Upload a structured dataset through the Streamlit interface.
- Natural-language data questions: Ask questions about the uploaded dataset without manually writing SQL or Python.
- AI-generated responses: Use Google Gemini Pro to interpret questions and generate dataset-aware responses.
- Data preprocessing: Prepare uploaded data for analysis, including handling data-quality concerns described in the project report.
- Natural-language data wrangling: Express operations such as renaming a column or dropping a column in plain English.
- Data visualization: Generate visual representations for analytical questions, including distributions, comparisons, trends, and correlations.
- Voice-based interaction: Convert spoken questions into text using speech recognition.
- Conversational interface: Interact with the dataset through a Streamlit chat experience.
Example use cases
Using an employee-style dataset containing fields such as Name, Department, Salary, and Experience, example questions could include:
- Which department has the highest average salary?
- Show the salary distribution.
- Compare average salary across departments.
- Is there a relationship between salary and experience?
- Drop the Gender column.
- Rename the Salary column to Monthly_Income.
The exact questions supported depend on the operations implemented in the current application.
Architecture
The following diagram represents the high-level workflow described in the project report. It is a conceptual view, not a verified trace of every function in the current app.py.
mermaid
**flowchart TD**
    A[User] --> B[Streamlit Interface]
    B --> C[CSV Upload]
    B --> D[Text or Voice Query]
    C --> E[CSV Reading and Data Preparation]
    E --> F[Structured Dataset]
    D --> G[Speech-to-Text, when voice is used]
    G --> H[Natural-Language Query]
    F --> I[Query Context / Data Access]
    H --> J[LangChain and Gemini Pro]
    I --> J
    J --> K[Response Generation]
    F --> L[Data Wrangling and Analysis]
    H --> L
    L --> M[Visualization]
    K --> N[Streamlit Chat Response]
    M --> N
    N --> A

**Main components**
Component	Responsibility
Streamlit	User interface, file upload, chat interaction, and result display
Python	Application logic and orchestration
Pandas	Tabular data loading, inspection, and transformation
Google Gemini Pro	Natural-language interpretation and response generation
LangChain	LLM application integration, as described in the report
Matplotlib / Seaborn	Data visualization
SpeechRecognition	Voice input and speech-to-text
ChromaDB / embeddings	Mentioned in the report as part of the proposed retrieval stack; verify actual use in source code before describing it as an implemented component


**Technology stack**
- Language: Python
- Interface: Streamlit
- Generative AI: Google Gemini Pro
- LLM orchestration: LangChain
- Data handling: Pandas
- Visualization: Matplotlib, Seaborn
- Speech input: SpeechRecognition
- Data ingestion: CSV processing; CSVLoader is referenced in the report
- Retrieval technology: ChromaDB and embeddings are referenced in the report; confirm implementation in the source before relying on this claim.
Repository structure
The current repository may contain a single app.py file. The structure below is a suggested organization for a future refactor; it does not imply that these modules already exist.
.
├── app.py
├── src/
│   ├── data_loader.py
│   ├── data_processing.py
│   ├── query_handler.py
│   ├── gemini_service.py
│   ├── speech_input.py
│   └── visualizations.py
├── assets/
├── screenshots/
├── tests/
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
Getting started
**Prerequisites**
- Python installed
- A Google Gemini API key with access to the model used by the application
- A working microphone, if using voice input
- The dependencies required by the source code
1. Clone the repository
git clone https://github.com/jewelreddys/Building-a-Chat--Based-Analysis-App-with-Streamlit-and-Gemini-Pro-with-Speech-Recognition.git
cd Building-a-Chat--Based-Analysis-App-with-Streamlit-and-Gemini-Pro-with-Speech-Recognition
2. Create and activate a virtual environment
python -m venv .venv
Windows:
.venv\Scripts\activate
macOS / Linux:
source .venv/bin/activate
3. Install dependencies
Once a requirements.txt file has been created and checked against the imports in app.py, install dependencies with:
pip install -r requirements.txt
4. Configure the Gemini API key
Create a local .env file or use Streamlit secrets, according to the configuration implemented in the application.

Example placeholder:
GOOGLE_API_KEY=replace_with_your_own_key
The variable name above is illustrative. Use the exact environment-variable name expected by app.py. Never commit a real API key, .env file, or credential to GitHub.

5. Run the application
streamlit run app.py
Open the local URL printed by Streamlit in your browser.
Screenshots and demonstration
Add genuine screenshots of your running application in the screenshots/ directory. Suggested captures:
1. Application home page and CSV upload.
2. Dataset preview after upload.
3. A natural-language question and its response.
4. A generated visualization.
5. A voice-query interaction.
6. A data-wrangling operation and the resulting dataset, if supported by the current code.
After adding the images, replace the placeholders below with the actual filenames:
![Application interface](screenshots/app-home.png)
![Dataset analysis](screenshots/data-analysis.png)
![Generated visualization](screenshots/visualization.png)
Do not use report figures as screenshots of the live application unless they genuinely show the running implementation.
Security and responsible use
- Keep API keys outside source control.
- Add .env and other secret-bearing files to .gitignore.
- Do not upload confidential, personal, or sensitive datasets to an external LLM service.
- Review and validate AI-generated analytical responses before relying on them.
- Handle malformed CSV files, missing values, unexpected encodings, and API errors gracefully.
- Avoid executing arbitrary code generated by an LLM.
- Explain to users when uploaded data or query context is sent to an external AI provider.
Current scope and future enhancements
The project report identifies the following as potential future directions:
- Predictive analytics and trend forecasting.
- Anomaly detection.
- Multilingual natural-language querying.
- SQL and NoSQL database integrations.
- Stronger data security and privacy controls.
These are roadmap ideas, not claims that the current application already implements them.
Project report
The academic report is titled:

Employee Data Insights: Building a Chat-Based Analysis App with Streamlit and Gemini Pro with Speech Recognition

It documents the motivation, architecture, technology choices, CSV analysis workflow, natural-language interaction, visualization approach, and voice-query concept.
Authors
- S. Jewel Reddy — GitHub
Institution: Vellore Institute of Technology (VIT), India
Program: Integrated M.Tech in Computer Science — Data Science specialization
**Notes for contributors**
This repository is an academic portfolio project. Before extending or deploying it, verify dependency versions, model/API compatibility, error handling, data privacy, and the implementation status of each capability described above.

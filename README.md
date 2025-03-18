Bank Statement Analyzer


Screenshot of the Bank Statement Analyzer interface (replace with an actual screenshot URL if available).

Overview
The Bank Statement Analyzer is a full-stack application designed to automate the analysis of bank statements and provide financial insights for loan decision-making. Built with a React frontend and a FastAPI backend, this tool extracts transactions from PDF statements, calculates key financial metrics (e.g., deposits, withdrawals, recurring expenses), and recommends loan eligibility based on a financial health score. A locally hosted chatbot, powered by Ollama, allows users to interactively query the analysis results for actionable advice, such as improving loan recommendations.

This project was developed as an MVP to address the inefficiencies of manual bank statement analysis in a financial institution, reducing processing time by over 90% and providing data-driven loan decisions.

Features
Automated Transaction Extraction: Parses bank statements in PDF format to extract transactions, handling various date formats and transaction types.
Financial Metrics Calculation: Calculates deposits, withdrawals, recurring expenses, outstanding loans, savings ratio, debt-to-income ratio, cash flow trend, and financial health score.
Loan Recommendation: Provides a data-driven loan eligibility recommendation based on a weighted financial health score.
Interactive Chatbot: Integrates a locally hosted Ollama-powered chatbot to answer user queries (e.g., "How can I improve my loan recommendation?") using the analysis results.
User-Friendly Interface: Built with React, offering a clean UI for uploading statements, viewing results, and interacting with the chatbot.
Tech Stack
Frontend: React, TypeScript, Axios, CSS
Backend: FastAPI (Python), pdfplumber, dateutil, requests
Chatbot: Ollama (locally hosted LLM, e.g., llama3)
Development Tools: Node.js, npm, Python 3.9+, Git
Prerequisites
Before running the project, ensure you have the following installed:

Node.js and npm (for the frontend): Install Node.js
Python 3.9+ (for the backend): Install Python
Ollama: For the chatbot, install Ollama and pull a model (e.g., ollama pull llama3).
Git: To clone the repository.
Installation
Clone the Repository:
bash

Collapse

Wrap

Copy
git clone https://github.com/[your-username]/bank-statement-analyzer.git
cd bank-statement-analyzer
Set Up the Backend:
Navigate to the backend directory:
bash

Collapse

Wrap

Copy
cd backend
Create a virtual environment and activate it:
bash

Collapse

Wrap

Copy
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install dependencies:
bash

Collapse

Wrap

Copy
pip install -r requirements.txt
Start the Ollama server with your chosen model:
bash

Collapse

Wrap

Copy
ollama run llama3
Run the FastAPI server:
bash

Collapse

Wrap

Copy
uvicorn main:app --reload
Set Up the Frontend:
Navigate to the frontend directory:
bash

Collapse

Wrap

Copy
cd ../src
Install dependencies:
bash

Collapse

Wrap

Copy
npm install
Start the React app:
bash

Collapse

Wrap

Copy
npm start
Access the Application:
Open your browser and go to http://localhost:3000 to access the frontend.
The backend runs on http://localhost:8000.
Usage
Upload a Bank Statement:
On the homepage, click "Choose File" to select a PDF bank statement.
Click "Analyze" to process the statement.
View Analysis Results:
The app displays financial metrics (e.g., deposits, withdrawals, recurring expenses), a financial health score, and a loan recommendation.
Scroll down to see the full transaction list.
Interact with the Chatbot:
Click the "Chat" button (bottom right) to open the chatbot window.
Ask questions like "How can I improve my loan recommendation?" to get personalized advice based on the analysis.
Project Structure
text

Collapse

Wrap

Copy
bank-statement-analyzer/
├── backend/                  # FastAPI backend
│   ├── main.py               # Main backend script with API endpoints
│   └── requirements.txt      # Backend dependencies
├── src/                      # React frontend
│   ├── App.tsx               # Main React component
│   ├── App.css               # Styling for the app
│   └── package.json          # Frontend dependencies
└── README.md                 # Project documentation
Sample Bank Statement Analysis
Input: IDFC First Bank statement (Apr 1, 2018 - Mar 31, 2019)
Output:
Deposits: $169,740.76
Withdrawals: $169,717.26
Recurring Expenses: $3,496 (loans), $500 (medical)
Financial Health Score: 50%
Loan Recommendation: No (due to high debt-to-income ratio and outstanding loans)
Chatbot Response: "To improve your loan recommendation, reduce withdrawals or pay off outstanding loans to lower your debt-to-income ratio."
Weaknesses and Future Improvements
Current Weaknesses
OCR Limitations: Struggles with noisy or incomplete OCR data (e.g., missing withdrawal amounts).
Date Parsing: Inconsistent handling of some date formats (e.g., "04 Sep19").
Categorization: Relies on keyword matching, missing nuanced transactions.
Chatbot: Limited prompt engineering reduces response quality.
Scalability: In-memory storage (analysis_results) isn’t suitable for multiple users.
Planned Improvements
Enhanced OCR: Use table-specific extraction and noise removal for better data capture.
Robust Parsing: Add more date format support and validation.
Advanced Categorization: Implement NLP for contextual transaction classification.
Improved Chatbot: Optimize prompts and add conversation memory.
Database Integration: Use SQLite for persistent storage.
UI Enhancements: Add visualizations (e.g., expense charts) and export options.
Contributing
Contributions are welcome! To contribute:

Fork the repository.
Create a feature branch (git checkout -b feature/YourFeature).
Commit your changes (git commit -m "Add YourFeature").
Push to the branch (git push origin feature/YourFeature).
Open a Pull Request.
Please ensure your code follows the existing style and includes tests where applicable.

License
This project is licensed under the MIT License. See the LICENSE file for details.

Acknowledgments
Built with inspiration from real-world financial analysis challenges.
Thanks to the open-source community for tools like FastAPI, React, and Ollama.

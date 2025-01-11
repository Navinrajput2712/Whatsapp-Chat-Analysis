 Whatsapp-chat-analysis" 

1. Set Up a Virtual Environment
Navigate to your project folder:

cd path/to/your/project
Create a virtual environment:

python -m venv venv_name
Activate the virtual environment:

On Windows:
venv_name\Scripts\activate
On macOS/Linux:
source venv_name/bin/activate
Verify the virtual environment is active (you should see (venv_name) in the terminal).

2. Install Dependencies from requirements.txt
If you have a requirements.txt file in your project, install dependencies:

pip install -r requirements.txt
If requirements.txt does not exist, manually install necessary libraries.

3. Install Project-Specific Dependencies
Install each library required by your project:

Streamlit:- pip install streamlit
Pandas:- pip install pandas
Matplotlib:- pip install matplotlib
Seaborn:- pip install seaborn
WordCloud:- pip install wordcloud
Emoji:- pip install emoji
URLExtract:- pip install urlextract

4. Export the requirements.txt File
Once all dependencies are installed, export them for future use:
pip freeze > requirements.txt
5. Run the Project
Make sure the virtual environment is active.
Run the project (e.g., if using Streamlit):
streamlit run app.py

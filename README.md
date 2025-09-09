# 📚 Book Recommender System

A Flask-powered web application that provides personalized book recommendations using a collaborative filtering machine learning model.



---

### Key Features ✨

* **🏆 Top Rated Books:** Browse a curated list of the top 50 books based on user ratings.
* **🧠 Smart Recommendations:** Get 5 book suggestions tailored to your taste by simply entering one book you love.
* **💻 Interactive UI:** A clean and responsive interface for a seamless user experience.



## 💻 Tech Stack

* **Backend:** Flask
* **Data Processing:** Pandas, NumPy
* **Machine Learning:** Scikit-learn (for Cosine Similarity)
* **Deployment:** Joblib (for loading pre-trained models and dataframes)
* **Frontend:** HTML, CSS

---

## 📂 Project Structure

The project is organized into several key components, including the Flask application, pre-processed data files, and HTML templates.

```
Book-Recommender-System/
├── templates/
│   ├── index.html        # Homepage displaying top 50 books
│   └── recommend.html      # Page for getting and displaying recommendations
├── app.py                  # Main Flask application file
├── books.pkl               # Serialized Pandas DataFrame with book details
├── popular.pkl             # Serialized DataFrame of the top 50 books
├── pt.pkl                  # Serialized pivot table (user-item matrix)
├── similarity_score.pkl    # Serialized similarity matrix (cosine scores)
├── requirements.txt        # List of Python dependencies
├── Model_file.ipynb        # Jupyter Notebook for the model training process
└── README.md               # Project documentation
```

---

## ⚙️ How the Recommendation Engine Works

This system uses a **collaborative filtering** approach to suggest books.

1.  **Data Preprocessing:** The initial datasets (Books, Users, Ratings) are cleaned and merged.
2.  **User-Item Matrix:** The model first builds a matrix where rows represent book titles and columns represent users. The values in this matrix are the ratings given by users to books.
3.  **Cosine Similarity:** It then calculates the **cosine similarity** between every pair of books based on their rating patterns. Books that are rated similarly by the same users are considered "close" to each other.
4.  **Making a Recommendation:**
    * When a user enters a book title, the system finds that book's index in the similarity matrix.
    * It retrieves the vector of similarity scores for that book.
    * It sorts these scores in descending order and picks the top 5 most similar books.
    * Finally, it fetches the details (title, author, image) for these recommended books from the `books.pkl` file and displays them to the user.


---

## 🚀 Quick Start: Running Locally

Follow these steps to get the project running on your machine.

### 1. Prerequisites

* Python 3.8+
* pip package manager

### 2. Setup

```sh
# Clone the repository
git clone [https://github.com/your-username/Book-Recommender-System.git](https://github.com/your-username/Book-Recommender-System.git)
cd Book-Recommender-System

# Create and activate a virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`

# Install all required packages
pip install -r requirements.txt
```

### 3. Run the Application

```sh
# Start the Flask development server
python app.py
```
🎉 **You're all set!** Open your browser and go to `http://127.0.0.1:5000`.

---

## 📂 Repository Overview

Here's a breakdown of the key files in this project:

| File/Folder          | Description                                                              |
| -------------------- | ------------------------------------------------------------------------ |
| `app.py`             | The main Flask application that handles all web routes and logic.        |
| `templates/`         | Contains the HTML files (`index.html`, `recommend.html`) for the UI.     |
| `Model_file.ipynb`   | Jupyter Notebook showing the entire ML model building process.           |
| `requirements.txt`   | A list of all Python dependencies required to run the project.           |
| `*.pkl` files        | Serialized Python objects (DataFrames, similarity matrix) used by the app. |

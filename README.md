# Tech Stack Recommender
### DecodeLabs | Artificial Intelligence Project 3

A beginner-friendly, content-based recommendation system that suggests the **Top 3 career roles** according to a user's technical skills.

## Project objective

The goal is to turn a user's skills into personalized career recommendations. The program compares the user's skill profile with the skills and descriptions of career roles in a dataset.

## Features

- Accepts at least **three skills** from the user.
- Checks that entered skills exist in the dataset.
- Uses **TF-IDF** to convert text into numerical feature vectors.
- Uses **Cosine Similarity** to measure how closely a role matches the user's profile.
- Sorts roles by similarity score in descending order.
- Displays the **Top 3** matching career roles with match percentages.
- Uses a CSV dataset that can be extended with more roles.

## Technology used

- Python 3
- pandas is not required
- scikit-learn
- CSV dataset

## Project structure

```text
tech-stack-recommender/
│
├── main.py
├── raw_skills.csv
├── requirements.txt
└── README.md
```

## How it works

```text
User enters 3 or more skills
           |
           v
Validate skills using dataset vocabulary
           |
           v
Create TF-IDF vectors for roles and user profile
           |
           v
Calculate Cosine Similarity scores
           |
           v
Sort roles from highest score to lowest
           |
           v
Display Top 3 career recommendations
```

### 1. Input

The user enters at least three skills, for example:

`Python, SQL, Machine Learning`

### 2. TF-IDF vectorization

TF-IDF stands for **Term Frequency–Inverse Document Frequency**. It gives numerical weights to terms. Terms that help distinguish a role from other roles can receive higher weights, while common terms receive lower weights.

### 3. Cosine Similarity

Cosine Similarity compares the direction of two vectors:

\[
\text{Cosine Similarity}(A,B)=
\frac{A \cdot B}{\|A\|\|B\|}
\]

A higher score means the user's skill text is more similar to a role's skill and description text.

### 4. Ranking and filtering

The program sorts all role scores in descending order and displays only the three highest positive matches.

## Installation and setup

### Step 1: Install Python

Install Python 3 from [python.org](https://www.python.org/downloads/).

During installation on Windows, select **Add Python to PATH**.

### Step 2: Open the project folder

Open this folder in VS Code.

### Step 3: Open the terminal

In VS Code, select **Terminal → New Terminal**.

### Step 4: Install the dependency

Run:

```bash
python -m pip install -r requirements.txt
```

If `python` does not work on Windows, try:

```bash
py -m pip install -r requirements.txt
```

### Step 5: Run the project

```bash
python main.py
```

Or on Windows:

```bash
py main.py
```

### Step 6: Enter your skills

When prompted, enter at least three different skills from the available list, separated by commas.

Example:

```text
Python, SQL, Machine Learning
```

The program will display the three closest career-role matches.

## Example input

```text
Python, SQL, Machine Learning
```

The exact scores and ranking are calculated from the included CSV data when the program runs.

## Dataset

`raw_skills.csv` contains career roles, their associated skills, and short descriptions. You can add more rows to expand the recommendation choices. Keep the same three column names:

- `role`
- `skills`
- `description`

Separate skills with commas. Use consistent skill names in the dataset.

## Important note

This is an educational **content-based filtering** project. It does not use other users' ratings or behavior (collaborative filtering). Its match percentage represents text similarity within this dataset; it is not a prediction of employment success.

## Future improvements

- Add more career roles and skills.
- Build a graphical interface using Streamlit.
- Allow users to rate recommendations.
- Add synonyms so related skill names can match.
- Save user profiles and recommendation history.

## Learning outcomes

- Python programming and CSV handling
- Text preprocessing and TF-IDF
- Vector representation
- Cosine Similarity
- Sorting and Top-N recommendation logic
- Basic recommendation-system design

---

**Project:** Artificial Intelligence – Project 3  
**Track:** DecodeLabs Industrial Training Kit, Batch 2026  
**Project title:** Tech Stack Recommender

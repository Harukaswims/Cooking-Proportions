# Cooking-Proportions
# 🍳 Recipe Ingredient Scaler

A Python-based command-line tool to automatically scale recipe ingredient quantities for any serving size. This project evaluates two different scaling models and provides an interactive tool for users to get ingredient amounts for their specific needs.



---
## ## Features

* **Dual Scaling Models**: Implements and evaluates two distinct scaling approaches:
    * **Ratio-Based Scaling**: A simple proportional model.
    * **Linear Interpolation**: A more robust model that accounts for base quantities.
* **Automatic Model Evaluation**: The script automatically runs a performance comparison between the two models using MAE (Mean Absolute Error) and MAPE (Mean Absolute Percentage Error) metrics.
* **Interactive Scaling Tool**: A user-friendly command-line interface that allows you to:
    * Choose a dish from the provided `paneer_recipes.json` file.
    * Select an ingredient to scale.
    * Enter any required serving size (including fractions) to get an accurate quantity estimate in grams.
* **Dynamic Data Handling**: The tool automatically reads the available serving sizes from the JSON data to build its scaling model, making it robust and adaptable.

---
## ## How to Run

This project is built with standard Python libraries and requires no external dependencies.

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/recipe-scaler.git](https://github.com/your-username/recipe-scaler.git)
    cd recipe-scaler
    ```

2.  **Ensure you have the data file:**
    Make sure the `paneer_recipes.json` file is in the same directory as the Python scripts.

3.  **Run the application:**
    ```bash
    python main.py
    ```
    The script will first run the model evaluation and then launch the interactive scaling tool.

---
## ## File Structure

* **`main.py`**: The main executable script. It contains the application logic, user interface, and orchestrates the evaluation and scaling processes.
* **`scaling_models.py`**: Defines the two scaling models (`RatioBasedScaler` and `LinearScaler`).
* **`evaluation.py`**: Contains the functions for the evaluation metrics (MAE and MAPE).
* **`paneer_recipes.json`**: The dataset containing ingredient quantities for four different paneer recipes across various serving sizes.

---
## ## Example Usage

When you run `main.py`, you will be guided through an interactive session like this:

```
--- Model Performance Evaluation ---

Model                     | Average MAE (grams)  | Average MAPE (%)
----------------------------------------------------------------------
Ratio-Based Scaling       | 13.4196              | 24.9697
Linear Interpolation      | 6.2657               | 15.9643

Available dishes: ['palak_paneer', 'shahi_paneer', 'matar_paneer', 'paneer_masala']
Which dish would you like to make? palak_paneer

Available ingredients: ['Onion', 'Garlic', 'Green chilli', '...']
Which ingredient do you want to scale? Paneer

How many servings do you need? (you can enter multiple, separated by commas): 7, 10.5

To scale 'Paneer', I'm using the quantities for 1 and 4 servings as a reference.

Here are your results:
  - For 7.0 servings, you will need 700.00 grams.
  - For 10.5 servings, you will need 1050.00 grams.

Happy cooking! 
```

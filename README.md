# Wordsearch

## Overview
This project is a Python-based word search generator that creates customizable word search puzzles. It allows users to generate word searches from predefined categories and save the puzzles as PDF files.

## Features
- Load words from JSON files
- Generate word search grids of customizable sizes
- Place words horizontally, vertically, or diagonally
- Randomly fill empty spaces in the grid with letters
- Display the word search grid in a Tkinter window
- Option to save the word search grid with solutions as a PDF

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/yourusername/word-search-generator.git
    cd word-search-generator
    ```

2. Install the required Python packages:
    ```sh
    pip install -r requirements.txt
    ```

3. Ensure you have the necessary JSON files with words in the `./JSON/` directory:
    - `animals.json`
    - `foods.json`
    - `colors.json`
    - `breakfast_food.json`

## Usage

1. **Load Words from JSON:**
    ```python
    def load_words_from_json(file_path):
        with open(file_path, 'r') as f:
            words = json.load(f)
        return words

    animals_words = load_words_from_json('./JSON/animals.json')
    foods_words = load_words_from_json('./JSON/foods.json')
    colors_words = load_words_from_json('./JSON/colors.json')
    breakfast_words = load_words_from_json('./JSON/breakfast_food.json')

    common_words = {
        'Animals': animals_words,
        'Foods': foods_words,
        'Colors': colors_words,
        "Breakfast": breakfast_words,
    }
    ```

2. **Generate Word Search:**
    ```python
    grid, word_positions = generate_word_search(words, num_words, size=10)
    ```

3. **Display Word Search in Tkinter Window:**
    ```python
    create_word_search_window(grid, word_positions, size, add_solution_to_pdf, filename)
    ```

4. **Save Word Search as PDF:**
    ```python
    create_solution_pdf(grid, filename, size)
    ```

5. **Button Click Event:**
    ```python
    on_button_clicked(name, grid_size, grade, word_type, num_words, print_pdf, filename)
    ```

## Example
Here's an example of generating a word search:
```python
name = "example"
grid_size = 10
grade = "Grade1"
word_type = "Animals"
num_words = 5
print_pdf = True
filename = "word_search_example.pdf"

on_button_clicked(name, grid_size, grade, word_type, num_words, print_pdf, filename)
```

## Project Structure
```python
word-search-generator/
├── JSON/
│   ├── animals.json
│   ├── foods.json
│   ├── colors.json
│   ├── breakfast_food.json
├── results/
├── word_search_generator.py
├── requirements.txt
└── README.md
```

## Contributing
We welcome contributions! Please fork the repository and submit pull requests for new features, bug fixes, or improvements.

## License
This project is licensed under the MIT License. See the LICENSE file for details.
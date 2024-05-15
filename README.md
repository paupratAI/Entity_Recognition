# Entity Recognition and POS Tagging Project

This project focuses on developing and evaluating models for Part-of-Speech (POS) tagging and Named Entity Recognition (NER) using CRFTagger. It includes various functions, model training, evaluation, and testing with real texts in Spanish and Dutch.

## Essential Functions

### get_token, get_token_POS, and get_token_entity
These functions extract specific parts of a tuple (token, POS, entity):
- `get_token()`: Returns a list of tokens.
- `get_token_POS()`: Returns a list of (token, POS) tuples.
- `get_token_entity()`: Returns a list of (token, entity) tuples.

### extract_entities
Identifies and returns entities from tagged words based on encoding ('BIO', 'IO', 'BIOW').

### evaluate_entities
Compares predicted entities with actual entities to calculate precision, recall, and F1 score.

## POS Tagging Model

### Model Development
A custom `FeatureGetterPOS` class was created with features like digit detection, capitalization, punctuation, prefix/suffix analysis, and context.

### Model Training
The model was trained separately for Spanish and Dutch, achieving:
- Spanish: 96.1% accuracy
- Dutch: 95.8% accuracy

## Entity Recognition Model with BIO Encoding

### Model Enhancements
Added features similar to POS tagging and included POS tags from the trained model.

### Evaluation Results

| Language   | Precision | Recall | F1 Score |
|------------|-----------|--------|----------|
| Spanish    | 0.783     | 0.768  | 0.776    |
| Dutch      | 0.769     | 0.715  | 0.741    |

## Other Encodings

### IO Encoding
Marks words inside entities with 'I' and others with 'O'.

| Language   | Precision | Recall | F1 Score |
|------------|-----------|--------|----------|
| Spanish    | 0.785     | 0.762  | 0.773    |
| Dutch      | 0.746     | 0.685  | 0.714    |

### BIOW Encoding
Extends BIO by adding 'W' for single-word entities.

| Language   | Precision | Recall | F1 Score |
|------------|-----------|--------|----------|
| Spanish    | 0.785     | 0.762  | 0.773    |
| Dutch      | 0.746     | 0.685  | 0.714    |

## Real Text Execution
Tested models on real texts in Spanish and Dutch, successfully recognizing entities with some misclassifications.

## Usage

1. Clone the repository.
2. Install required packages.
3. Place text files in the `data` folder.
4. Use provided functions to tokenize, tag, and evaluate the text.

## Future Improvements

1. Enhance entity type classification.
2. Optimize feature selection for different languages.
3. Expand training data for better generalization.


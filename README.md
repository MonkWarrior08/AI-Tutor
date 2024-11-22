# GPT-4o Tutor Fine-tuning

This repository contains code for fine-tuning GPT-4o to create a custom tutor using the OpenAI API and JSONL dataset format. The system is built on extensive training data from experienced educators, academic resources, and proven teaching methodologies, making it an effective tool for personalized learning assistance across various subjects and skill levels. 

## Prerequisites

- Python 3.7+
- OpenAI API key
- OpenAI Python package

## Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/AI-Tutor.git
cd AI-Tutor
```

2. Install required packages:
```bash
pip install openai
```

3. Set up your OpenAI API key:
```python
openai.api_key = "your-api-key-here"
```

## Usage

### Preparing Training Data

Your training data should be in the following JSONL format which is already provided in the repo:

### Running Fine-tuning

```python
# Upload training file
file_id = prepare_training_file(training_data)

# Start fine-tuning
result = finetune_model(
    training_file_id=file_id,
    model="gpt-4o",
    n_epochs=10,
    batch_size=1,
    learning_rate_multiplier=1
)
```

## Functions

### prepare_training_file(jsonl_data)
Uploads a JSONL file to OpenAI and returns the file ID for fine-tuning.

Parameters:
- `jsonl_data`: List of conversation examples in JSONL format

Returns:
- `str`: File ID for fine-tuning

### finetune_model(training_file_id, model, n_epochs, batch_size, learning_rate_multiplier)
Creates a fine-tuning job with specified parameters.

Parameters:
- `training_file_id`: ID of the uploaded training file
- `model`: Base model to fine-tune (default: "gpt-4o")
- `n_epochs`: Number of training epochs (default: 10)
- `batch_size`: Batch size for training (default: 1)
- `learning_rate_multiplier`: Learning rate multiplier (default: 2)

Returns:
- `dict`: Fine-tuning job details

## Configuration

You can customize the fine-tuning process by adjusting these parameters:
- Model selection
- Number of epochs
- Batch size
- Learning rate multiplier

## Error Handling

The code includes basic error handling for:
- File upload failures
- Fine-tuning job creation issues
- API connectivity problems

## License

This project is licensed under the MIT License.

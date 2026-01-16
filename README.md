# LinkedIn Profile Comparison Tool

This project uses Large Language Models (LLMs) to compare LinkedIn profiles and score candidates for networking potential based on a user's profile.

## Overview

The tool analyzes two LinkedIn profiles:
- **User Profile**: Your own LinkedIn profile (stored in `user.json`)
- **Candidate Profile**: A potential connection's profile (stored in `candidate.json`)

Using the LLaMA 3.1 model via Ollama, it evaluates the candidate's suitability for networking with the user across several dimensions:
- **Approachability**: How easy and appropriate it would be to reach out
- **Usefulness**: Potential value the candidate can provide
- **Context Alignment**: How well backgrounds and interests match
- **Mentorship**: Potential for mentorship opportunities
- **Total Score**: Overall networking value

## Prerequisites

- Python 3.7+
- [Ollama](https://ollama.ai/) installed and running
- LLaMA 3.1 model downloaded (`ollama pull llama3.1`)

## Installation

1. Clone this repository:
   ```bash
   git clone <repository-url>
   cd devfest-llm
   ```

2. Install Ollama and pull the LLaMA model:
   ```bash
   # Install Ollama (follow instructions at https://ollama.ai/)
   ollama pull llama3.1
   ```

3. Ensure Ollama is running in the background.

## Usage

1. Prepare your profile data:
   - Place your LinkedIn profile JSON in `user.json`
   - Place the candidate's LinkedIn profile JSON in `candidate.json`

2. Run the comparison:
   ```bash
   python compare.py
   ```

3. View the results in the terminal output.

## Profile JSON Format

The JSON files should contain LinkedIn profile data with the following structure:

```json
{
  "linkedin_url": "https://www.linkedin.com/in/username/",
  "name": "Full Name",
  "location": "City, Country",
  "about": "About section text",
  "open_to_work": false,
  "experiences": [
    {
      "position_title": "Job Title",
      "institution_name": "Company Name",
      "description": "Job description"
    }
  ],
  "educations": [
    {
      "degree": "Degree Name",
      "institution_name": "School Name"
    }
  ],
  "interests": [],
  "accomplishments": [],
  "contacts": []
}
```

## How It Works

1. **Profile Conversion**: Converts JSON profiles to readable text format
2. **AI Analysis**: Sends both profiles to LLaMA with a detailed prompt for evaluation
3. **Scoring**: Parses the AI response to extract numerical scores
4. **Output**: Displays the comparison results

## Dependencies

- `ollama` - For running LLaMA models locally
- `json` - Built-in Python library for JSON handling

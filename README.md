# Project Title: AI Chatbot with Real-Time Information

This repository contains a Python project for an advanced chatbot using the Groq API, providing real-time information and managing conversation history in a structured way.

## Repository Structure

```
project-root/
├── Chatbot.py
└── Data/
    └── Chatlog.json
```

- `Chatbot.py`: Main application script with the chatbot logic.
- `Data/Chatlog.json`: Stores chat logs and message history.

***

## Features

- **AI-powered Chat**: Integrates with Groq's API for advanced, up-to-date conversational AI responses.
- **Real-Time Context**: Supplies every conversation with current date and time details.
- **Persistent Chat History**: Maintains user and assistant transcripts in a JSON file for continuity.
- **Configurable System Message**: Easily customize Assistant name, user name, and behavioral instructions.
- **Environment Variables**: Load your Groq API key and credentials safely using the `.env` file.

***

## Getting Started

### Prerequisites

- Python 3.8 or higher
- Required libraries: `groq`, `python-dotenv`

Install dependencies:

```bash
pip install groq python-dotenv
```

### Setup

1. **Clone the repository** and navigate to its directory.

2. **Create a `.env` file** at the root and add:

    ```
    GROQ_API_KEY=your_actual_groq_api_key
    ```

3. **Ensure the directory structure**:

    - `Chatbot.py` is in your main project folder.
    - `Data/` folder exists at the same level, with an (initially empty) `Chatlog.json` file.

***

## Usage

Run the chatbot from the terminal:

```bash
python Chatbot.py
```

You will be prompted for your query, and the assistant will answer according to instructions.

***

## Code Guidelines

- **API Key Security**: Never hard-code your Groq API key. Use environment variables and `dotenv` to keep secrets safe.
- **Path Handling**: File paths use `r"Data\Chatlog.json"` (Windows-style). Ensure compatibility or adapt for cross-platform support if needed.
- **Error Handling**: On FileNotFound, `Chatlog.json` is created as an empty list (`[]`). If any exception arises during chat, it resets the chat log.
- **Message Structure**: All chat turns, both user and assistant, are logged as dictionaries with `"role"` and `"content"`.
- **System Prompt**: All core instructions are contained in the system message (`System`). Modify it to control chatbot behavior.
- **Real-Time Injection**: Every response is supplied with up-to-date time, date, and day information using `RealtimeInformation()`.
- **Answer Formatting**: Responses are stripped of excess whitespace before display (handled by `AnswerModifier`).

***

## Best Practices

- Keep `Chatbot.py` clean and modular. Add utility functions for new features.
- Regularly back up or rotate `Chatlog.json` if running for long periods.
- If targeting non-English users, remember: the bot always replies in English as per default instructions.
- Avoid outputting time unless specifically requested by the user (enforced by the system prompt).
- Do not mention training data, provide notes, or answer in other languages without changing the system prompt.

***

## Customization

- Change assistant/user names by editing the respective variables at the top of `main.py`.
- Edit the system prompt string to tweak AI instructions or response policies.

***

## License

Include an appropriate license if open-sourcing your project.

***

## Disclaimer

This project is for educational use; review and adapt the error handling and credential management for production deployments.

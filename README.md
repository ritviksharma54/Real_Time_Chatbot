# Real-Time Voice AI with Gemini

This project is a web application that enables real-time voice conversations with Google's Gemini AI model. It features client-side Voice Activity Detection (VAD) for hands-free operation, allowing users to speak naturally and receive spoken responses from the AI.

## Features

*   **Real-time Voice Input:** Speak directly into your browser.
*   **Hands-Free Operation:** Client-side Voice Activity Detection (VAD) automatically detects when you start and stop speaking.
*   **AI Conversation:** Powered by Google's Gemini 1.5 Flash model for intelligent responses.
*   **Text-to-Speech (TTS):** AI responses are spoken back to the user using the browser's built-in speech synthesis.
*   **Visual Feedback:** Includes an audio visualizer for microphone input and status indicators for different states (listening, processing, speaking).
*   **Conversation History:** Displays the ongoing chat.
*   **Customizable Voice Output:** Options to change the AI's voice (from available system voices), speed, and pitch.
*   **(Temporarily Disabled) Barge-in:** Functionality for the user to interrupt the AI while it's speaking (can be re-enabled and tuned).

## Prerequisites

Before you begin, ensure you have the following installed:

1.  **Python 3.7+**
2.  **pip** (Python package installer)
3.  **FFmpeg:** This is crucial for audio format conversion on the server-side.
    *   **Windows:** Download from [ffmpeg.org](https://ffmpeg.org/download.html), extract, and add the `bin` directory to your system's PATH.
    *   **macOS (using Homebrew):** `brew install ffmpeg`
    *   **Linux (using apt):** `sudo apt update && sudo apt install ffmpeg`
    Verify installation by typing `ffmpeg -version` in your terminal.
4.  **A modern web browser** that supports:
    *   WebRTC (`getUserMedia`)
    *   Web Audio API
    *   `MediaRecorder` API
    *   Web Speech API (`speechSynthesis`)
    *   Socket.IO
    (Most modern browsers like Chrome, Firefox, Edge, Safari should work).
5.  **Microphone:** Required for voice input.

## Setup and Installation

1.  **Clone the Repository (or Create Project Folder):**
    If you have this project in a Git repository:
    ```bash
    git clone <repository-url>
    cd <repository-name>
    ```
    Otherwise, create a project folder and place `app.py` and the `templates` folder (containing `index.html`) inside it.

2.  **Create a `templates` Folder:**
    Inside your project directory, create a folder named `templates`.
    ```bash
    mkdir templates
    ```
    Place the `index.html` file inside this `templates` folder. Your project structure should look like:
    ```
    your-project-folder/
    ├── app.py
    ├── templates/
    │   └── index.html
    └── requirements.txt  (You will create this next)
    ```

3.  **Set up Google Gemini API Key:**
    *   Obtain an API key from [Google AI Studio](https://aistudio.google.com/app/apikey).
    *   Set this API key as an environment variable named `GEMINI_API_KEY`.
        *   **Linux/macOS:**
            ```bash
            export GEMINI_API_KEY="YOUR_API_KEY_HERE"
            ```
            (Add this to your `.bashrc`, `.zshrc`, or shell profile for persistence).
        *   **Windows (Command Prompt):**
            ```bash
            set GEMINI_API_KEY=YOUR_API_KEY_HERE
            ```
        *   **Windows (PowerShell):**
            ```powershell
            $env:GEMINI_API_KEY="YOUR_API_KEY_HERE"
            ```
            (For persistence on Windows, set it through System Properties -> Environment Variables).

4.  **Create a Python Virtual Environment (Recommended):**
    ```bash
    python -m venv venv
    ```
    Activate the virtual environment:
    *   **Linux/macOS:**
        ```bash
        source venv/bin/activate
        ```
    *   **Windows:**
        ```bash
        venv\Scripts\activate
        ```

5.  **Install Python Dependencies:**
    Create a `requirements.txt` file (provided below) in your project root and run:
    ```bash
    pip install -r requirements.txt
    ```


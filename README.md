# InkScript AI Research Studio

InkScript AI is a powerful, client-side web application designed to digitize, transcribe, and analyze handwritten notes and PDF documents. By leveraging advanced multimodal AI vision models, it converts messy handwriting, mathematical formulas, and diagrams into structured, editable, and exportable digital formats.

The entire application is contained within a single file, making it highly portable and easy to deploy.

## ✨ Key Features

*   **Dual AI Engine Support:** 
    *   **Local Privacy (Ollama):** Run vision models entirely on your local machine (e.g., `qwen2.5vl:7b`) for 100% offline and private transcription.
    *   **Cloud Power (Google Gemini):** Use the Gemini 3 Flash Vision API for blazing-fast, highly accurate transcriptions.
*   **Notebook Mode:** A specialized transcription mode that creates a faithful digital replica of your physical notebook. It preserves layouts, side remarks, and inline math, rendering it onto a virtual ruled paper interface using a handwriting-style font.
*   **Advanced Math Rendering:** Built-in KaTeX support accurately renders LaTeX mathematical formulas, equations, and fractions natively within the editor.
*   **Multiple Transcription Modes:** Tailor the AI's output to your needs:
    *   Notebook Page (Faithful replica)
    *   Verbatim Transcription
    *   Cleaned & Formatted
    *   Summary & Action Items
    *   Research Notes (Concepts, citations, open questions)
    *   Structured (Tables & Graphs)
    *   Translation to English
*   **AI-Powered Study Tools:** Select your transcribed text and instantly generate summaries, flashcards, key terms, research questions, or find citations using the AI assistant.
*   **Rich Export Options:** Download your notes as an interactive HTML Notebook, Markdown (`.md`), Plain Text (`.txt`), Word Document (`.doc`), or Print to PDF.
*   **Built-in Library:** Automatically saves your transcriptions to your browser's local storage for easy retrieval later.

## 🚀 Getting Started

Since the app is fully contained within a single HTML file, installation is incredibly simple.

1. Download the `inkscript_ai_ollama.html` file to your computer.
2. Double-click the file to open it in any modern web browser (Chrome, Edge, Firefox, Safari).

## ⚙️ AI Engine Configuration

To use InkScript AI, you must configure an AI engine. Click the **key icon** in the top right corner of the app to open the settings.

### Option 1: Local AI via Ollama (Free & Private)
If you want to process documents offline without sending data to the cloud:
1. Install [Ollama](https://ollama.com/) on your machine.
2. Open your terminal/command prompt and download a vision model. We recommend Qwen 2.5 VL for handwriting:
   ```bash
   ollama pull qwen2.5vl:7b
   ```
3. **CRITICAL:** You must allow the web browser to communicate with Ollama. Set the `OLLAMA_ORIGINS` environment variable to `*` and restart the Ollama application.
   * *Windows:* `set OLLAMA_ORIGINS="*"`
   * *Mac/Linux:* `export OLLAMA_ORIGINS="*"`
4. In the InkScript settings, select **Ollama**, ensure the address is correct (default: `http://localhost:11434`), type your model name, and click "Test & list models".

### Option 2: Google Gemini (Cloud API)
1. Get an API key from Google AI Studio.
2. In the InkScript settings, select **Google Gemini**, paste your API key into the input field, and click **Save Key**. The key is stored securely in your browser's `localStorage`.

## 🛠️ Built With

*   **HTML/CSS/JS:** Pure client-side vanilla JavaScript.
*   **Tailwind CSS:** For responsive, modern styling and Dark Mode.
*   **Lucide Icons:** Clean and lightweight iconography.
*   **KaTeX:** Fast math typesetting for the web.
*   **PDF.js:** Mozilla's library for rendering PDF files directly in the browser.

## 📝 Usage Notes

*   **File Limits:** When using Gemini, standard API rate limits apply. When using Ollama, processing speed depends entirely on your local GPU/CPU hardware.
*   **PDFs:** The app converts PDF pages into high-resolution images in the browser before sending them to the AI for transcription. Large PDFs may take some time to process.
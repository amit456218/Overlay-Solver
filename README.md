# Screen Overlay Problem-Solving Assistant

An always-on-top, transparent overlay that captures on-screen text, queries OpenAI for solutions, and displays responses directly over your workspace.

## Table of Contents

* [Features](#features)
* [Installation](#installation)
* [Configuration](#configuration)
* [Usage](#usage)
* [Architecture](#architecture)
* [Hotkeys](#hotkeys)
* [Dependencies](#dependencies)
* [Contributing](#contributing)
* [License](#license)

## Features

* **Stealth Mode:** Seamlessly integrates without interrupting your workflow—frameless, click-through, and excluded from screen captures.
* **Universal Text Capture:** Grab any on-screen text (code snippets, error messages, documentation, etc.) via screenshot and OCR.
* **Real-Time Problem Solving:** Sends extracted text to OpenAI’s GPT-4, providing solutions, explanations, or next steps.
* **Flexible Display:** Pops up contextual responses (text, code, diagrams) without leaving your current application.
* **Configurable Shortcuts:** Customize hotkeys for toggling visibility, capturing screens, and quitting the app.

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/overlay-assistant.git
   cd overlay-assistant
   ```
2. (Optional) Set up a virtual environment:

   ```bash
   python -m venv venv
   source venv/bin/activate  # macOS/Linux
   venv\Scripts\activate    # Windows
   ```
3. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```
4. Install Tesseract OCR:

   * Download and install from [Tesseract OCR GitHub](https://github.com/tesseract-ocr/tesseract).

## Configuration

Modify the `Config` parameters in `main.py` or a separate `config.py`:

| Parameter         | Description                                     | Default                |
| ----------------- | ----------------------------------------------- | ---------------------- |
| `OPENAI_API_KEY`  | Your OpenAI API key                             | \`\`                   |
| `TESSERACT_PATH`  | Path to the Tesseract executable                | Platform-specific path |
| `ISLAND_WIDTH`    | Width of the overlay control bar                | `700`                  |
| `ISLAND_HEIGHT`   | Height of the overlay control bar               | `90`                   |
| `SOLUTION_WIDTH`  | Width of the solution popup window              | `900`                  |
| `SOLUTION_HEIGHT` | Height of the solution popup window             | `600`                  |
| `TOGGLE_KEY`      | Hotkey to show/hide the overlay                 | `ctrl+]`               |
| `CAPTURE_KEY`     | Hotkey to capture screen and request a solution | `ctrl+shift+]`         |
| `QUIT_KEY`        | Hotkey to quit the application                  | `ctrl+q`               |

## Usage

1. Verify Tesseract is installed and `TESSERACT_PATH` is correct.
2. Run the application:

   ```bash
   python main.py
   ```
3. From any application:

   * Press **capture** hotkey or click the 📸 button to capture text.
   * View the AI-generated solution in the popup.
   * Toggle the overlay with the **toggle** hotkey.
   * Quit with the **quit** hotkey.

## Architecture

```
main.py
├── Config            # Application settings
├── StealthWidget     # Transparent, click-through window base class
├── ScreenOverlay     # Control bar UI for capture and status
├── APIWorker         # Asynchronous OpenAI API requester
└── SolutionPopup     # Popup window for displaying AI responses
```

## Hotkeys

| Action           | Default Shortcut |
| ---------------- | ---------------- |
| Toggle Overlay   | `Ctrl+]`         |
| Capture & Solve  | `Ctrl+Shift+]`   |
| Quit Application | `Ctrl+Q`         |

## Dependencies

* Python 3.8+
* [PyQt5](https://pypi.org/project/PyQt5/)
* [pillow](https://pypi.org/project/Pillow/)
* [pytesseract](https://pypi.org/project/pytesseract/)
* [keyboard](https://pypi.org/project/keyboard/)
* [requests](https://pypi.org/project/requests/)

## Contributing

1. Fork the repository.
2. Create a branch for your feature:

   ```bash
   ```

git checkout -b feature-name

````
3. Make your changes and commit:
   ```bash
git commit -m "Add new feature"
````

4. Push to your fork and open a pull request.

## License

*No license specified.* All rights reserved. Please contact the repository owner for licensing details.

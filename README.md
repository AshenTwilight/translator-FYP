# LinguaFlash

**LinguaFlash** is a real-time language translation tool built using FastAPI, Google Gemini 1.5 Flash, Gradio, and Supervisor. This tool leverages advanced AI models to provide fast and accurate translations between various languages.

## Features
- Real-time translation of text to multiple languages.
- User-friendly interface with Gradio.
- Scalable and robust architecture using FastAPI and Supervisor.
- Powered by Google Gemini 1.5 Flash for high-quality translations.

## Prerequisites
- Python 3.7+
- An API key for Google Gemini 1.5 Flash
- `pip` for package installation

## Installation
1. **Clone the repository:**
    ```bash
    git clone https://github.com/yourusername/LinguaFlash.git
    cd LinguaFlash
    ```

2. **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3. **Set up the environment variables:**
    - Create a `.env` file in the root directory.
    - Add your Google Gemini 1.5 Flash API key:
    ```plaintext
    api_key=YOUR_API_KEY_HERE
    ```

## Usage
### Running the FastAPI Server
1. **Navigate to the project directory:**
    ```bash
    cd LinguaFlash
    ```

2. **Start the FastAPI server:**
    ```bash
    uvicorn main:app --host 0.0.0.0 --port 8000 --reload
    ```

### Running the Gradio Interface
1. **In a new terminal window, navigate to the project directory:**
    ```bash
    cd LinguaFlash
    ```

2. **Start the Gradio interface:**
    ```bash
    python app.py
    ```

### Using Supervisor
Supervisor can be used to manage both the FastAPI server and the Gradio interface.

1. **Install Supervisor:**
    ```bash
    sudo apt-get install supervisor
    ```

2. **Copy the `supervisord.conf` file to `/etc/supervisor/conf.d/`:**
    ```bash
    sudo cp supervisord.conf /etc/supervisor/conf.d/linguaflash.conf
    ```

3. **Update Supervisor and start the processes:**
    ```bash
    sudo supervisorctl update
    sudo supervisorctl start all
    ```

## API Endpoint
### `/translate/`
- **Method:** POST
- **Request Body:**
    ```json
    {
        "text": "Hello, world!",
        "target_language": "es"
    }
    ```
- **Response:**
    ```json
    {
        "translation": "¡Hola, mundo!"
    }
    ```

## Contributing
Feel free to fork the repository and submit pull requests. For major changes, please open an issue to discuss what you would like to change.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
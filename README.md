AI Ticket Search Bot
A semantic search and recommendation system for IT service tickets, built using Python, Sentence Transformers, FAISS, and Flask.
Easily search historical tickets by service name, error type, or keyword and get relevant past resolutions via a web UI.

Features
1.Semantic search: Finds relevant tickets even with varied wording using AI embeddings.
2.Service & error awareness: Supports RTS, RPT, RDT, MNP-FNSADPTER, VTR, and PSO services.
3.Resolutions at a glance: Returns ticket number, title, and resolution for each match.
4.Web UI: Simple browser-based search interface.
5.Dockerized: Run anywhere with a single command.

Quick Start
1. Clone the Repository
git clone https://github.com/yourusername/ticket_search_bot.git
cd ticket_search_bot

2. Build the Docker Image

docker build -t ticket-bot .

3. Prepare Data & Build Index
These steps are run inside the container, but you can also run them locally if you prefer:

docker run --rm -v $(pwd):/app ticket-bot python src/prepare_data.py
docker run --rm -v $(pwd):/app ticket-bot python src/build_index.py

4. Run the Search Bot Web UI

docker run -p 5000:5000 -v $(pwd):/app ticket-bot
Visit http://localhost:5000 in your browser.

Usage
Enter a keyword, service name, or error type (e.g., Kubernetes RPT, Memory leak PSO, CPU overload).

The bot will return up to 5 most relevant past tickets with their resolutions.

Customizing Ticket Data
Edit or replace input/tickets.csv with your own ticket dump.

Ensure your CSV contains these columns:
ticket_number,title,description,resolution

Re-run prepare_data.py and build_index.py after updating the CSV.

Technologies Used
Python 3.11

Sentence Transformers
FAISS
Flask
Docker

Contributing
Pull requests and issues are welcome!
Feel free to fork, improve, or adapt for your organization.

Author
Made with ❤️ by Ketan mehetre
Your GitHub Profile

Happy ticket searching!

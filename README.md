# KindleScribe Automatic Downloader API
This Python script automatizes the process of storing `PDF` files sent by a *Kindle Scribe*.
## APIs
The whole script is based on Google's `Gmail API`, enabling it to parse email metadata and find the temporary link for the `PDF`.
> When a `PDF` is shared through a Kindle Scribe *send to email* function, the file is hosted for 30 days on Amazon's servers in order to make it downloadable.
> The `URL` is then embedded in a link on the email sent to the user.

Once the `URL` has been found, the script fetches it via:
```bash
curl -s -o kindle_pdfs/<filename>.pdf '<pdf_link>'
```
## Essential files
- `credentials.json` downloadable after generating an **ID client OAuth 2.0** via the Google API Dashboard.
- `token.json` generated after loggin in via a link.
## Running the code
Before running the code it is essential to install the `requirements.txt` dependencies, it is recommended to use a python virtual environment:
```bash
python3 -m venv .venv
source .venv/bin/activate
```
> Use the appropriate `activate` accordingly (eg. `activate.fish` for `fish` shell)
```bash
pip3 install -r requirements.txt
```
The code is then runnable as following:
```bash
python3 main.py
```
The `PDFs` will be saved in the `kindle_pdfs/` folder.
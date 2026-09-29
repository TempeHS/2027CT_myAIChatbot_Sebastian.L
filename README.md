# ChungBot

ChungBot is a student-built chatbot learning project. It provides a browser-based chat interface, uses a Flask API to receive messages, and uses ChatterBot to generate replies. It includes an educational disclaimer and directs users seeking crisis support towards human support services.

## Technologies used

- Python and Flask — web application and `/chat` API
- ChatterBot and ChatterBot Corpus — chatbot responses and training data
- spaCy — language processing
- SQLite — chatbot data storage
- HTML, CSS, JavaScript and Bootstrap 5 — chat interface
- pytest — automated testing

## Installation and running

1. Open a terminal in the project folder.
2. Install the project dependencies:

   `python -m pip install -r requirements.txt`

3. Download the spaCy English model:

   `python -m spacy download en_core_web_sm`

4. If startup reports `No module named 'yaml'`, install PyYAML:

   `python -m pip install pyyaml`

5. Start the application:

   `python app.py`

6. Wait for training to finish, then open `http://localhost:5000/`.

The initial training may take 10–30 seconds. Keep the terminal running while using the page.

## Testing

Run the automated tests with `pytest test_chatbot.py`.

### User acceptance testing (UAT)

| Test                                              | Expected result                    | Actual result                                                    | Status |
| ------------------------------------------------- | ---------------------------------- | ---------------------------------------------------------------- | ------ |
| Open the application in a browser                 | Chat page and disclaimer appear    | Chat page and disclaimer appeared                                | Passed |
| Send a message through the browser                | The message and a bot reply appear | Message and bot reply appeared                                   | Passed |
| Submit an empty message through the browser       | No empty message is sent           | No empty message was sent                                        | Passed |
| Enter more than 500 characters in the browser     | Input is limited to 500 characters | Input was limited to 500 characters                              | Passed |
| Run automated tests with `pytest test_chatbot.py` | All tests pass                     | 10 passed in 7.71 seconds, using Python 3.13.15 and pytest 9.1.1 | Passed |

All listed checks passed. An earlier HTTP 502 was reported, but the application has since been tested successfully. Add the test date if required for your UAT evidence.

The automated tests cover crisis detection, `/chat` responses and input sanitisation. They do not verify that the application loads in a browser. The test date was not provided; record it when completing the UAT evidence.

## Author and disclaimer

**Author:** Sebastian Lam ([@sebbylam](https://github.com/SebbyLam))

ChungBot is an educational project. Its replies may be inaccurate and should not be treated as professional advice or a substitute for speaking with a real person. If you need support, speak with a trusted adult or contact an appropriate support service.

## Licence

This project is licensed under the GNU General Public License version 3.0. See the `LICENSE` file.

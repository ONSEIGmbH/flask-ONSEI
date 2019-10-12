# Flask Dialogflow
[![Build Status](https://travis-ci.com/ONSEIGmbH/flask-dialogflow.svg?branch=master)](https://travis-ci.com/ONSEIGmbH/flask-dialogflow)

Flask Dialogflow is a Flask extension to build [Dialogflow](https://dialogflow.com/)
agents. It aims to shine through the following features:

* A familiar Flask extension structure that handles the mundane stuff behind
  the scenes
* Robust JSON serialization and deserialization of the entire Dialogflow and
  Actions on Google API to native Python classes
* A simple API for high-level Google Assistant features
* Special template features for voice assistants
* Support for multi-platform agents and extensibility to new platforms
* Integration with the Flask CLI and shell
* Helpers to test an agent
* A comprehensive test suite

Here is a quick example:

```python
from flask import Flask
from flask_dialogflow.agent import DialogflowAgent

app = Flask(__name__)
agent = DialogflowAgent(app)

@agent.handle(intent='HelloWorld')
def hello_world(conv):
    conv.google.ask('Hello world!')
    return conv
```

For more information, check out the Tutorial and the API [documentation](https://flask-dialogflow.readthedocs.io/en/latest/).

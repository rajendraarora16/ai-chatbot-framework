<img src="https://i.ibb.co/vLR1wpG/logo.png" width="280"/>

[![Join the chat at https://gitter.im/ai-chatbot-framework/Lobby](https://badges.gitter.im/ai-chatbot-framework/Lobby.svg)](https://gitter.im/ai-chatbot-framework/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) [![Build Status](https://travis-ci.com/alfredfrancis/ai-chatbot-framework.svg?branch=master)](https://travis-ci.com/alfredfrancis/ai-chatbot-framework.svg?branch=master)



### An AI Chatbot framework built in Python

Building a chatbot can sound daunting, but it’s totally doable. AI Chatbot Framework is an AI powered conversational dialog interface built in Python. With this tool, it’s easy to create Natural Language conversational scenarios with no coding efforts whatsoever. The smooth UI makes it effortless to create and train conversations to the bot and it continuously gets smarter as it learns from conversations it has with people. AI Chatbot Framework can live on any channel of your choice (such as Messenger, Slack etc.) by integrating it’s API with that platform.

You don’t need to be an expert at artificial intelligence to create an awesome chatbot that has AI capabilities. With this boilerplate project you can create an AI powered chatting machine in no time.There may be scores of bugs. So feel free to contribute  via pull requests.

![](https://image.ibb.co/eMJ9Wx/Screen_Shot_2018_04_28_at_1_45_28_PM.png)

### Installation

### Using docker-compose (Recommended) 
```sh
docker-compose build
docker-compose up -d
docker-compose exec iky_backend python manage.py migrate
```

### Using Docker
```sh

# build docker images
docker build -t iky_backend:2.0.0 .
docker build -t iky_gateway:2.0.0 frontend/.

# start a mongodb server
docker run --name mongodb -d mongo:3.6

# start iky backend
docker run -d --name=iky_backend --link mongodb:mongodb -e="APPLICATION_ENV=Production" iky_backend:2.0.0

# setup default intents
docker exec -it iky_backend python manage.py migrate

# start iky gateway with frontend
docker run -d --name=iky_gateway --link iky_backend:iky_backend -p 8080:80 iky_gateway:2.0.0

```

### without docker

* Setup Virtualenv and install python requirements
```sh
virtualenv -p python3 venv
source venv/bin/activate
python manage.py migrate
python run.py
```
* Production
```sh
APPLICATION_ENV="Production" gunicorn -k gevent --bind 0.0.0.0:8080 run:app
```
* Open http://localhost:8080/

#### Update Frontend Dist
* Run Development mode
```sh
cd frontend
npm install
ng serve
```
* Take Production build
```sh
cd frontend
ng build --prod --optimize
```

### Heroku
[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

* add your dev/production configurations in config.py

### DB

#### Restore
You can import some default intents using following steps

- goto http://localhost:8080/agent/default/settings
- click 'choose file'
- choose 'examples/default_intents.json file'
- click import

### Screenshots

![](https://image.ibb.co/i9ReWx/Screen_Shot_2018_04_28_at_1_38_15_PM.png)
---
![](https://image.ibb.co/ivXKWx/Screen_Shot_2018_04_28_at_1_38_36_PM.png)
---
![](https://image.ibb.co/nf9Bdc/Screen_Shot_2018_04_28_at_1_38_57_PM.png)
---
![](https://image.ibb.co/b4q1dc/Screen_Shot_2018_04_28_at_1_43_06_PM.png)
### Tutorial

Checkout this basic tutorial on youtube,

[![IMAGE ALT TEXT HERE](https://preview.ibb.co/fj9N3v/Screenshot_from_2017_04_05_03_11_04.png)](https://www.youtube.com/watch?v=S1Fj7WinaBA)


Watch tutorial on [Fullfilling your Chatbot Intent with an API Call - Recipe Search Bot](https://www.youtube.com/watch?v=gqO69ojLobQ)

Please visit my [website](http://alfredfrancis.github.io) to see my personal chatbot in action

### Todos
 *  Write Unit Tests
 *  Multilingual Intent Classifier
 *  PyCRFSuite to sklearn-crfsuite migration
 *  Support follow up conversations
 
 ### Dependencies documentations
* [SKLearn documentation](http://scikit-learn.org/)
* [CRFsuite documentation](http://www.chokkan.org/software/crfsuite/)
* [python CRfSuite](https://python-crfsuite.readthedocs.io/en/latest/)

## Contributors

[![](https://sourcerer.io/fame/alfredfrancis/alfredfrancis/ai-chatbot-framework/images/0)](https://sourcerer.io/fame/alfredfrancis/alfredfrancis/ai-chatbot-framework/links/0)[![](https://sourcerer.io/fame/alfredfrancis/alfredfrancis/ai-chatbot-framework/images/1)](https://sourcerer.io/fame/alfredfrancis/alfredfrancis/ai-chatbot-framework/links/1)[![](https://sourcerer.io/fame/alfredfrancis/alfredfrancis/ai-chatbot-framework/images/2)](https://sourcerer.io/fame/alfredfrancis/alfredfrancis/ai-chatbot-framework/links/2)[![](https://sourcerer.io/fame/alfredfrancis/alfredfrancis/ai-chatbot-framework/images/3)](https://sourcerer.io/fame/alfredfrancis/alfredfrancis/ai-chatbot-framework/links/3)[![](https://sourcerer.io/fame/alfredfrancis/alfredfrancis/ai-chatbot-framework/images/4)](https://sourcerer.io/fame/alfredfrancis/alfredfrancis/ai-chatbot-framework/links/4)[![](https://sourcerer.io/fame/alfredfrancis/alfredfrancis/ai-chatbot-framework/images/5)](https://sourcerer.io/fame/alfredfrancis/alfredfrancis/ai-chatbot-framework/links/5)[![](https://sourcerer.io/fame/alfredfrancis/alfredfrancis/ai-chatbot-framework/images/6)](https://sourcerer.io/fame/alfredfrancis/alfredfrancis/ai-chatbot-framework/links/6)[![](https://sourcerer.io/fame/alfredfrancis/alfredfrancis/ai-chatbot-framework/images/7)](https://sourcerer.io/fame/alfredfrancis/alfredfrancis/ai-chatbot-framework/links/7)

**Free Software, Hell Yeah!**
<hr></hr>

_Made with :heart: at God's Own Country_.

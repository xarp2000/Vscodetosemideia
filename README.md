from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello_world():
    return '<h1>Hello, World!</h1>'

app.run(debug=True)

from flask import Flask
import random

app = Flask(__name__)
facts_list = ["Elon Musk afirma que as redes sociais são projetadas para nos manter dentro da plataforma, para que passemos o máximo de tempo possível visualizando conteúdo.",            
              "De acordo com um estudo realizado em 2018, mais de 50% das pessoas entre 18 e 34 anos se consideram dependentes de seus smartphones.", 
              "As redes sociais têm seus pontos positivos e negativos, e devemos estar conscientes de ambos ao utilizá-las.", 
              "O estudo da dependência tecnológica é uma das áreas mais relevantes da pesquisa científica moderna."]

@app.route("/")
def index():
    return f'<h1>Olá! nesta pagina você encontrará alguns fatos sobre dependências tecnológicas!</h1><a href="/random_fact">Veja um fato aleatório!</a>' 

@app.route("/random_fact")
def facts():
    return f'<p>{random.choice(facts_list)}</p><br><a href="/">Voltar para a página inicial</a>'

app.run(debug=True)

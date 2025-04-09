## simulador-bacbo/
├── app.py
├── requirements.txt
├── render.yaml
├── templates/
│   └── index.html
from flask import Flask, render_template, request
import random

app = Flask(__name__)

def rolar_dados():
    return random.randint(1, 6), random.randint(1, 6)

@app.route("/", methods=["GET", "POST"])
def index():
    resultado = None
    if request.method == "POST":
        dados_jogador1 = rolar_dados()
        dados_jogador2 = rolar_dados()
        soma1 = sum(dados_jogador1)
        soma2 = sum(dados_jogador2)

        if soma1 > soma2:
            vencedor = "Jogador 1"
        elif soma2 > soma1:
            vencedor = "Jogador 2"
        else:
            vencedor = "Empate"

        resultado = {
            "dados1": dados_jogador1,
            "dados2": dados_jogador2,
            "soma1": soma1,
            "soma2": soma2,
            "vencedor": vencedor
        }

    return render_template("index.html", resultado=resultado)

if __name__ == "__main__":
    app.run(debug=True)flask
gunicorn
**Neguinho51/Neguinho51** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub simulador-bacbo/services:
  - type: web
    name: simulador-bacbo
    env: python
    buildCommand: ""
    startCommand: gunicorn app:git init
git add .
git commit -m "Versão inicial do simulador Bac Bo"
git branch -M main
git remote add origin https://github.com/neguinho51/SEU_REPO.git
git push -u origin main



Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

# 

**URL:** https://raw.githubusercontent.com/GusttavoJaguar/Auttoma--o-de-tarefas/main/main.py

---

# PRINCIPAIS COMANDOS PYAUTOGUI							|
# pyautogui.click -> clicar no mouse					|
# pyautogui.write -> escrever texto						|
# pyautogui.press -> apertar uma teclas					|
# pyautogui.hotkey -> atalho(combinação de teclas)		|
#-------------------------------------------------------

# PASSO A PASSO 
# Passo 1: Entrar no sistema da empresa
	# localhost
import pyautogui
import time
import pandas


# Abrir o navegador
pyautogui.PAUSE = 2

pyautogui.press("win")
pyautogui.write("firefox")
pyautogui.press("enter")
# Entrar no link 
link = "http://localhost/ControleDeEstoque"
pyautogui.write(link)
pyautogui.press("enter")

# Esperar o site carregar
time.sleep(5)

# Passo 2: Fazer login http://localhost/Controle%20de%20estoque/Controle%20de%20estoque/Controle%20de%20estoque/index.html
pyautogui.click(x=688, y=322)
pyautogui.click(x=532, y=311)
pyautogui.click(x=532, y=311)
pyautogui.hotkey("ctrl", "a")
pyautogui.write("gusttavojaguar@gmail.com")
pyautogui.press("tab")
pyautogui.write("*******")
pyautogui.press("enter")
pyautogui.click(x=678, y=357)

# Passo 3: Importar a base de dados de produtos

tabela = pandas.read_csv("produtos.csv")
print(tabela)

for linha in tabela.index:

# Passo 4: Cadastrar 1 produto

	pyautogui.click(x=340, y=376)

	nome = tabela.loc[linha, "nome"]

	# Preencher campos 
	pyautogui.write(str(nome))
	pyautogui.press("tab")
	pyautogui.write(str(tabela.loc[linha, "quantidade"]))
	pyautogui.press("tab")
	pyautogui.write(str(tabela.loc[linha, "preco"]))
	pyautogui.press("tab")
	pyautogui.write(str(tabela.loc[linha,"cod"]))
	pyautogui.press("tab")
	pyautogui.write(str(tabela.loc[linha,"descricao"]))
	pyautogui.press("tab")
	pyautogui.write(str(tabela.loc[linha,"categoria"]))

	pyautogui.press("tab")
	pyautogui.press("enter")


# Passo 5: Repetir o cadastro para todos os produtos


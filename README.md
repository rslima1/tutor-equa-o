# tutor-equação
import tkinter as tk
from tkinter import messagebox

# Funções para calcular e verificar as respostas
def calcular():
    global etapa
    if etapa == 1:
        resposta_usuario = resposta_1.get()
        if resposta_usuario == resp_esp1:
            messagebox.showinfo("Sucesso", "Você acertou a primeira etapa!")
            etapa += 1
        else:
            messagebox.showwarning("Atenção", "Sua resposta não está correta, tente novamente. \n \nDica: iguale as equações das retas f e g.")                              
    elif etapa == 2:
        resposta_usuario = resposta_2.get()
        if resposta_usuario == resp_esp2:
            messagebox.showinfo("Sucesso", "Você acertou a segunda etapa!")
            etapa += 1
        else:
            messagebox.showwarning("Atenção", "Sua resposta não está correta, tente novamente. \nDica: Isole o X em um dos lados da equação. \n \nObserve o exemplo: \n3x + 24 = -x + 4 \n3x + x = 4 - 24 \n4x = -20")
    elif etapa == 3:
        resposta_usuario = resposta_3.get()
        if resposta_usuario == resp_esp3:
            messagebox.showinfo("Sucesso", "Você acertou a terceira etapa!")
            etapa += 1
        else:
            messagebox.showwarning("Atenção", "Sua resposta não está correta, tente novamente. \nDica: Divida ambos os membros da equação por 4. \n \nObserve o exemplo: \n4x = -20 \n4x/4 = -20/4 \nx = -5")
    elif etapa == 4:
        resposta_usuario = resposta_4.get()
        if resposta_usuario == resp_esp4:
            messagebox.showinfo("Sucesso", "Você acertou a quarta etapa!\nPonto de intersecção das retas f e g: x = -5, y = 9")
            etapa += 1
        else:
            messagebox.showwarning("Atenção", "Sua resposta não está correta, tente novamente. \nDica: substitua o valor de X em alguma das equações f ou g. \n \nObserve o exemplo: \nf: y = 3x + 24 \ny = 3.(-5) + 24 \ny = -15 + 24 \ny = 9")
    else:
        messagebox.showinfo("Fim", "Você completou todas as etapas do problema!")

# Função para exibir a próxima etapa
def proxima_etapa():
    global etapa
    if etapa == 1:
        pergunta_1.config(text="Encontre o ponto de intersecção de duas retas dadas, f: y = 3x + 24 e g: y = -x + 4")
        resposta_1.config(state="normal")
        resposta_1.delete(0, 'end')
        verificar_button.config(command=calcular)
    elif etapa == 2:
        pergunta_2.config(text="Nossa equação agora é 3x + 24 = -x + 4")
        resposta_2.config(state="normal")
        resposta_2.delete(0, 'end')
        verificar_button.config(command=calcular)
    elif etapa == 3:
        pergunta_3.config(text="Nossa equação agora é 4x = -20")
        resposta_3.config(state="normal")
        resposta_3.delete(0, 'end')
        verificar_button.config(command=calcular)
    elif etapa == 4:
        pergunta_4.config(text="Escreva o valor de y =")
        resposta_4.config(state="normal")
        resposta_4.delete(0, 'end')
        verificar_button.config(command=calcular)
    else:
        messagebox.showinfo("Fim", "Você completou todas as etapas do problema!")

# Configuração inicial
etapa = 1
resp_esp1 = "3x+24=-x+4"
resp_esp2 = "4x=-20"
resp_esp3 = "x=-5"
resp_esp4 = "9"

# Criar uma janela
root = tk.Tk()
root.title("Tutor de Matemática")

# Etapa 1
pergunta_1 = tk.Label(root, text="Encontre o ponto de intersecção de duas retas dadas, f: y = 3x + 24 e g: y = -x + 4")
pergunta_1.pack()
resposta_1 = tk.Entry(root)
resposta_1.pack()
verificar_button = tk.Button(root, text="Verificar", command=calcular)
verificar_button.pack()
resposta_1.config(state="normal")  # Inicialment, ativar a caixa de resposta

# Botão para a próxima etapa
proximo_button = tk.Button(root, text="Próxima Etapa", command=proxima_etapa)
proximo_button.pack()

# Etapa 2
pergunta_2 = tk.Label(root, text="", state="normal")
pergunta_2.pack()
resposta_2 = tk.Entry(root)
resposta_2.pack()
verificar_button = tk.Button(root, text="Verificar", command=calcular)
verificar_button.pack()
resposta_2.config(state="normal")

proximo_button = tk.Button(root, text="Próxima Etapa", command=proxima_etapa)
proximo_button.pack()


# Etapa 3
pergunta_3 = tk.Label(root, text="", state="normal")
pergunta_3.pack()
resposta_3 = tk.Entry(root)
resposta_3.pack()
verificar_button = tk.Button(root, text="Verificar", command=calcular)
verificar_button.pack()
resposta_3.config(state="normal")

proximo_button = tk.Button(root, text="Próxima Etapa", command=proxima_etapa)
proximo_button.pack()


# Etapa 4
pergunta_4 = tk.Label(root, text="", state="normal")
pergunta_4.pack()
resposta_4 = tk.Entry(root)
resposta_4.pack()
verificar_button = tk.Button(root, text="Verificar", command=calcular)
verificar_button.pack()
resposta_4.config(state="normal")

root.mainloop()


from tkinter import *


def botao_numero_clicado(numero):
    entrada.insert(END, numero)


janela = Tk()
janela.title("Calculadora")
janela.geometry("320x480")
janela.resizable(False, False)


entrada = Entry(janela, font=("Arial", 24))
entrada.grid(row=0, columnspan=4, sticky="w")


botao_soma = Button(janela, text="+", fg="white", bg="#333", command=lambda: botao_clicado(botao_soma))
botao_soma.grid(row=1, column=0, sticky="w")

botao_subtracao = Button(janela, text="-", fg="white", bg="#333", command=lambda: botao_clicado(botao_subtracao))
botao_subtracao.grid(row=1, column=1, sticky="w")

botao_multiplicacao = Button(janela, text="*", fg="white", bg="#333", command=lambda: botao_clicado(botao_multiplicacao))
botao_multiplicacao.grid(row=1, column=2, sticky="w")

botao_divisao = Button(janela, text="/", fg="white", bg="#333", command=lambda: botao_clicado(botao_divisao))
botao_divisao.grid(row=1, column=3, sticky="w")


def botao_numero_clicado(numero):
    entrada.insert(END, numero)

for i in range(3):
    for j in range(3):
        numero = i * 3 + j
        botao_numero = Button(janela, text=numero, fg="black", bg="#ccc", command=lambda numero=numero: botao_numero_clicado(numero))
        botao_numero.grid(row=i+2, column=j, sticky="w")

botao_zero = Button(janela, text="0", fg="black", bg="#ccc", command=lambda: botao_numero_clicado(0))
botao_zero.grid(row=5, columnspan=3, sticky="w")

botao_ponto = Button(janela, text=".", fg="black", bg="#ccc", command=lambda: botao_numero_clicado("."))
botao_ponto.grid(row=5, column=3, sticky="e")


botao_limpar = Button(janela, text="C", fg="white", bg="#ff0000", command=lambda: entrada.delete(0, END))
botao_limpar.grid(row=6, columnspan=4, sticky="w")

janela.mainloop()

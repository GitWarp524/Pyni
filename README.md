# Importa a biblioteca Tkinter
import tkinter as tk
from tkinter import messagebox

# Cria a janela principal
janela = tk.Tk()
janela.title("Meu Gerenciador de Tarefas")
janela.geometry("400x300") # Largura x Altura

# Campo de entrada para a tarefa
entrada_tarefa = tk.Entry(janela, width=40)
entrada_tarefa.pack(pady=10) # Adiciona um espaçamento vertical

# Função para adicionar tarefa (seria mais complexa com lógica real)
def adicionar_tarefa():
    tarefa = entrada_tarefa.get()
    if tarefa: # Verifica se o campo não está vazio
        lista_tarefas.insert(tk.END, tarefa) # Adiciona ao final da lista
        entrada_tarefa.delete(0, tk.END) # Limpa o campo de entrada
    else:
        messagebox.showwarning("Atenção", "Por favor, digite uma tarefa.")

# Botão para adicionar tarefa
botao_adicionar = tk.Button(janela, text="Adicionar Tarefa", command=adicionar_tarefa)
botao_adicionar.pack()

# Lista para exibir as tarefas
lista_tarefas = tk.Listbox(janela, width=50, height=10)
lista_tarefas.pack(pady=10)

# Inicia o loop principal da aplicação (mantém a janela aberta)
janela.mainloop()

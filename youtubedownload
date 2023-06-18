import tkinter as tk
from tkinter import messagebox
from pytube import YouTube

def baixar():
    link = entry_link.get()
    try:
        video = YouTube(link, use_oauth=True, allow_oauth_cache=True)
        video = video.streams.get_highest_resolution()
        titulo = video.title
        resposta = messagebox.askquestion("Confirmação", f"Você deseja mesmo fazer o download do vídeo '{titulo.upper()}'?")
        if resposta == "yes":
            try:
                video.download()
                messagebox.showinfo("Sucesso", "Download concluído com sucesso.")
            except:
                messagebox.showerror("Erro", "Desculpe, ocorreu um erro.")
    except:
        messagebox.showerror("Erro", "Ocorreu um erro ao obter informações do vídeo.")

# Cria a janela
janela = tk.Tk()
janela.title("Downloader de Vídeo")
janela.geometry("400x150")

# Cria os widgets
label_link = tk.Label(janela, text="Insira o link do vídeo:")
label_link.pack()

entry_link = tk.Entry(janela, width=50)
entry_link.pack()

button_download = tk.Button(janela, text="Baixar", command=baixar)
button_download.pack()

# Inicia o loop principal da janela
janela.mainloop()

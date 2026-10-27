import tkinter as tk
from tkinter import messagebox
import time
import subprocess
import os

def iniciar_broma():
    # 1. Primera ventana: Run? con opciones Sí / No
    respuesta = messagebox.askyesno("Prompt", "Run?")
    
    if respuesta: # Si el usuario presiona "Sí"
        # 2. Segunda ventana con la advertencia en inglés
        messagebox.showwarning(
            "Warning", 
            "I am not responsible if I destroy your PC, it's yours not mine!"
        )
        
        # 3. Esperar 30 segundos sin que pase nada visible
        time.sleep(30)
        
        # 4. Tercera ventana de error en inglés
        messagebox.showerror("Error", "Bro, this is my power")
        
        # 5. Abrir el CMD e iniciar el bucle de texto
        # El comando 'color 0a' pone las letras en verde tipo "hacker"
        prog_cmd = (
            "@echo off\n"
            "title System Critical Error\n"
            "color 0a\n" 
            ":loop\n"
            "echo ERROR: Your files were decrypted!\n"
            "timeout /t 1 >nul\n"
            "goto loop\n"
        )
        
        # Creamos el archivo temporal para el CMD
        with open("fake_error.bat", "w") as f:
            f.write(prog_cmd)
            
        # Abrimos la ventana del CMD ejecutando el archivo
        subprocess.Popen(["cmd.exe", "/c", "start", "fake_error.bat"], shell=True)
        
        # 6. Mantener el CMD abierto durante 2 minutos (120 segundos)
        time.sleep(120)
        
        # Cerramos todas las ventanas de CMD abiertas por el script
        subprocess.run(["taskkill", "/f", "/im", "cmd.exe"], stdout=subprocess.DEVNULL, stderr=subprocess.DEVNULL)
        
        # Borramos el archivo temporal .bat para no dejar rastro en la carpeta
        if os.path.exists("fake_error.bat"):
            os.remove("fake_error.bat")
            
        # 7. Ventana final revelando la broma
        messagebox.showinfo("Joke's Over", "Bro, this was a fake virus wasa")
        
    else:
        # Si el usuario presiona "No", el programa se cierra sin hacer nada
        pass

if __name__ == "__main__":
    # Ocultar la ventana principal de fondo de tkinter
    root = tk.Tk()
    root.withdraw()
    iniciar_broma()

# Little-Programs

#Fancy Bear

#This is a GUI front for s #powershelk linking script
#This script simply links #together othet scripts
#in sequence order, while #waiting fot current one
#to complete. Includes staus #screen.


Import required modules

import tkinter as tk
import subprocess

Define main window

root = tk.Tk()
root.title("Custom Microsoft Windows Installation")
root.geometry("600x400")

Define variables

current_script = tk.StringVar()
percent_complete = tk.DoubleVar()

Define functions

def run_script(script):
subprocess.call(["powershell.exe", script])

def start_installation():
run_script("script1.ps1")
current_script.set("Script 1")
percent_complete.set(10)
root.update()
run_script("script2.ps1")
current_script.set("Script 2")
percent_complete.set(20)
root.update()
run_script("script3.ps1")
current_script.set("Script 3")
percent_complete.set(30)
root.update()
# Repeat for remaining scripts

Define widgets

current_script_label = tk.Label(root, textvariable=current_script)
current_script_label.pack()

progress_bar = tk.ttk.Progressbar(root, orient="horizontal", length=400, mode="determinate", maximum=100, variable=percent_complete)
progress_bar.pack()

start_button = tk.Button(root, text="Start Installation", command=start_installation)
start_button.pack()

dancing_bear = tk.PhotoImage(file="dancing_bear.gif")
dancing_bear_label = tk.Label(root, image=dancing_bear)
dancing_bear_label.pack()

Start GUI



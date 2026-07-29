import tkinter as tk
import random

root = tk.Tk()
root.title("❤️ Sorry Maruf ❤️")
root.geometry("700x500")
root.configure(bg="#FFD6E8")  # soft pink background

# Title
title = tk.Label(root, text="SORRY MARUF 💔", font=("Arial", 26, "bold"), bg="#FFD6E8", fg="red")
title.pack(pady=40)

# Question Label - will update later
question = tk.Label(root, text="", font=("Arial", 18, "bold"), bg="#FFD6E8", fg="deeppink", wraplength=600)
question.pack(pady=20)

# Final message label
love = tk.Label(root, text="", font=("Arial", 22, "bold"), bg="#FFD6E8", fg="red")
love.pack(pady=10)

def next_page():
    title.config(text="")  # hide title
    question.config(text="Did you accept my sorry? ❤️")
    start_btn.pack_forget() # hide start button
    yes_btn.place(x=220, y=360)
    no_btn.place(x=420, y=360)

def yes_clicked():
    love.config(text="❤️ I LOVE YOU ❤️\n\nPlease never leave me 🥺")
    yes_btn.place_forget()  # hide buttons
    no_btn.place_forget()

def move_no(event):
    x = random.randint(50, 550)
    y = random.randint(250, 430)
    no_btn.place(x=x, y=y)

# Buttons
start_btn = tk.Button(root, text="Continue ❤️", font=("Arial", 14), bg="hotpink", fg="white", command=next_page)
start_btn.pack(pady=10)

yes_btn = tk.Button(root, text="YES", font=("Arial", 14), bg="green", fg="white", command=yes_clicked)
no_btn = tk.Button(root, text="NO", font=("Arial", 14), bg="red", fg="white")
no_btn.bind("<Enter>", move_no)  # mouse gele palabe

root.mainloop()

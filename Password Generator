import random
import string
import tkinter as tk
from tkinter import ttk, PhotoImage
from tkinter import messagebox

def rgb_to_hex(rgb):
    return "#%02x%02x%02x" % rgb
def generate_password(length=12):
    characters = string.ascii_letters + string.digits + string.punctuation
    password = ''.join(random.choice(characters) for _ in range(length))
    return password

def generate_multiple_passwords(num_passwords, length=12):
    passwords = [generate_password(length) for _ in range(num_passwords)]
    return passwords

def generate_passwords_button_clicked():
    try:
        length = int(length_entry.get())
        num_passwords = int(num_passwords_entry.get())
    except ValueError:
        messagebox.showerror("Error", "Please enter valid numeric values.")
        return

    if length <= 0 or num_passwords <= 0:
        messagebox.showerror("Error", "Please enter positive values for length and number of passwords.")
        return

    passwords = generate_multiple_passwords(num_passwords, length)

    result_text.delete(1.0, tk.END)
    result_text.insert(tk.END, "Generated Passwords:\n")
    for i, password in enumerate(passwords, start=1):
        result_text.insert(tk.END, f"Password {i}: {password}\n")

root = tk.Tk()
root.title("Amazing Password Generator")



frame = tk.Frame(root,bg=rgb_to_hex((10,40,90)))
frame.place(relx=0.5, rely=0.5, anchor="center")


length_label = tk.Label(frame, text="Enter Length:",bg=rgb_to_hex((10,40,100)),fg="white")
length_label.grid(row=0, column=0, pady=5, sticky="w")

length_entry = ttk.Entry(frame)
length_entry.grid(row=0, column=1, pady=5, padx=5)

num_passwords_label = tk.Label(frame, text="Enter Number of Passwords:",bg=rgb_to_hex((10,40,100)),fg="white")
num_passwords_label.grid(row=1, column=0, pady=5, sticky="w")

num_passwords_entry = ttk.Entry(frame)
num_passwords_entry.grid(row=1, column=1, pady=5, padx=5)

generate_button = ttk.Button(frame, text="Generate Passwords", command=generate_passwords_button_clicked)
generate_button.grid(row=2, columnspan=2, pady=10)

result_text = tk.Text(frame, height=8, width=40, wrap="word", font=("Helvetica", 10))
result_text.grid(row=3, columnspan=2, pady=5)

root.mainloop()

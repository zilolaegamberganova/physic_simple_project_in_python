# physic_simple_project_in_python
This project includes a variety of physics problems with detailed solutions. It is designed to help students understand key concepts and improve their problem-solving skills in physics.
This is the code
import tkinter as tk
from tkinter import ttk

# Asosiy oyna
window = tk.Tk()
window.title("Fizika hisoblagichi")
window.geometry("500x400")

# Tabs (Kinematika va Energiyalar)
notebook = ttk.Notebook(window)
tab1 = ttk.Frame(notebook)  # Kinematika
tab2 = ttk.Frame(notebook)  # Energiyalar

notebook.add(tab1, text="Kinematika")
notebook.add(tab2, text="Energiyalar")
notebook.pack(expand=True, fill="both")

# ======== Kinematika Bo‘limi ========
def calculate_kinematics():
    try:
        distance = float(entry_distance.get())
        time = float(entry_time.get())
        speed = distance / time
        label_result_kinematics.config(text=f"Tezlik: {speed:.2f} m/s")
    except ValueError:
        label_result_kinematics.config(text="Iltimos, masofa va vaqtni to‘g‘ri kiriting!")

# Masofa va vaqt kiritish
label_distance = tk.Label(tab1, text="Masofa (m):")
label_distance.pack()
entry_distance = tk.Entry(tab1)
entry_distance.pack()

label_time = tk.Label(tab1, text="Vaqt (s):")
label_time.pack()
entry_time = tk.Entry(tab1)
entry_time.pack()

# Hisoblash tugmasi
button_calculate_kinematics = tk.Button(tab1, text="Hisoblash", command=calculate_kinematics)
button_calculate_kinematics.pack(pady=10)

# Natija ko‘rsatish
label_result_kinematics = tk.Label(tab1, text="", font=("Arial", 12))
label_result_kinematics.pack()

# ======== Energiyalar Bo‘limi ========
def calculate_energy():
    try:
        mass = float(entry_mass.get())
        velocity = float(entry_velocity.get())
        height = float(entry_height.get())
        # Kinetik energiya
        kinetic_energy = 0.5 * mass * velocity**2
        # Potensial energiya
        potential_energy = mass * 9.8 * height
        label_result_energy.config(text=f"Kinetik E: {kinetic_energy:.2f} J\nPotensial E: {potential_energy:.2f} J")
    except ValueError:
        label_result_energy.config(text="Iltimos, massani, tezlikni va balandlikni to‘g‘ri kiriting!")

# Massa, tezlik va balandlik kiritish
label_mass = tk.Label(tab2, text="Massa (kg):")
label_mass.pack()
entry_mass = tk.Entry(tab2)
entry_mass.pack()

label_velocity = tk.Label(tab2, text="Tezlik (m/s):")
label_velocity.pack()
entry_velocity = tk.Entry(tab2)
entry_velocity.pack()

label_height = tk.Label(tab2, text="Balandlik (m):")
label_height.pack()
entry_height = tk.Entry(tab2)
entry_height.pack()

# Hisoblash tugmasi
button_calculate_energy = tk.Button(tab2, text="Hisoblash", command=calculate_energy)
button_calculate_energy.pack(pady=10)

# Natija ko‘rsatish
label_result_energy = tk.Label(tab2, text="", font=("Arial", 12))
label_result_energy.pack()

# Asosiy oynani ishga tushirish
window.mainloop()

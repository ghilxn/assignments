# simple gas mileage calculator
# formula: MPG = miles / gallons

import tkinter as tk   # Tkinter is just Python’s built-in GUI library

def calculate_mpg():
    gallons = float(entry_gallons.get())
    miles = float(entry_miles.get())
    mpg = miles / gallons
    result_label.config(text=f"Miles per gallon: {mpg:.2f}")

# make a window
window = tk.Tk()
window.title("Gas Mileage Calculator")
window.geometry("300x200")

# gallons input
tk.Label(window, text="Gallons of gas the car holds:").pack()
entry_gallons = tk.Entry(window)
entry_gallons.pack()

# miles input
tk.Label(window, text="Miles it can be driven on a full tank:").pack()
entry_miles = tk.Entry(window)
entry_miles.pack()

# button to calculate
tk.Button(window, text="Calculate MPG", command=calculate_mpg).pack(pady=10)

# label to show result
result_label = tk.Label(window, text="Miles per gallon:")
result_label.pack()

# keep window open
window.mainloop()

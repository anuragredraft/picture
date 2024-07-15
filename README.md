# picture
from PIL import Image
import tkinter as tk
from tkinter import colorchooser

def choose_color():
    # Open the color chooser dialog
    color_code = colorchooser.askcolor(title="Choose a color")
    if color_code[1] is not None:
        create_image(color_code[1])

def create_image(color):
    # Create an image with the selected color
    img = Image.new('RGB', (200, 200), color)
    img.save("colored_image.png")
    print(f"Image created with color {color} and saved as colored_image.png")

# Create the main window
window = tk.Tk()
window.title("Color Picker")
window.geometry("400x300")

# Button to open the color chooser dialog
choose_color_button = tk.Button(window, text="Choose a color", command=choose_color)
choose_color_button.pack(pady=20)

# Run the main event loop
window.mainloop()

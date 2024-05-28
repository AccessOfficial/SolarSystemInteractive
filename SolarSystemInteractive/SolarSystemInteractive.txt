# Import required libraries
import tkinter as tk
from PIL import ImageTk, Image

def show_description(planet_name):
    descriptions = {
        "Sun": "The Sun is the star at the center of the Solar System. It is a nearly perfect sphere of hot plasma.",
        "Mercury": "Mercury is the closest planet to the Sun and the smallest planet in the solar system. It has a diameter of about 4,880 kilometers (3,032 miles). Mercury has a heavily cratered surface, resembling the Earth's Moon, due to its lack of atmosphere to erode impact craters. It has extreme temperature variations, with surface temperatures reaching up to 430°C (800°F) on the side facing the Sun and dropping to -180°C (-290°F) on the side facing away. Mercury has a very thin atmosphere, primarily composed of oxygen, sodium, hydrogen, helium, and potassium.",
        "Venus": "Venus is the second planet from the Sun. It is a terrestrial planet. Venus is often called Earth's 'sister planet' due to its similar size and composition. It is the second planet from the Sun and has a diameter of about 12,104 kilometers (7,521 miles). Venus has a thick atmosphere primarily composed of carbon dioxide, with clouds of sulfuric acid that obscure its surface. Its surface is rocky and heavily cratered, with large volcanic plains and mountains. Venus has a runaway greenhouse effect, making it the hottest planet in the solar system, with surface temperatures reaching up to 470°C (880°F).",
        "Earth": "Earth is the third planet from the Sun and the only astronomical object known to harbor life. It has a diameter of about 12,742 kilometers (7,918 miles). Earth has a diverse range of ecosystems, including oceans, forests, deserts, and polar regions. Its atmosphere primarily consists of nitrogen (78%) and oxygen (21%), with traces of other gases. Earth has a single natural satellite, the Moon, which plays a significant role in tides and stabilizing the planet's rotation.",
        "Mars": "Mars is the fourth planet from the Sun and the second-smallest planet in the Solar System. Mars is often called the 'Red Planet' due to its reddish appearance caused by iron oxide on its surface. It is the fourth planet from the Sun and has a diameter of about 6,779 kilometers (4,212 miles). Mars has the largest volcano and the deepest canyon in the solar system: Olympus Mons and Valles Marineris, respectively. Its thin atmosphere is primarily carbon dioxide with traces of nitrogen and argon. Mars has polar ice caps composed of water and frozen carbon dioxide. Recent evidence suggests that Mars may have had liquid water on its surface in the past, raising questions about the possibility of ancient life. ",
        "Jupiter": "Jupiter is the largest planet in the Solar System. It is a gas giant. Jupiter is the largest planet in the solar system, often referred to as a 'gas giant.' It is the fifth planet from the Sun and has a diameter of about 139,820 kilometers (86,881 miles). Jupiter has a banded appearance due to its thick atmosphere composed mostly of hydrogen and helium. The Great Red Spot, a massive storm system, is a prominent feature on Jupiter's surface. Jupiter has a strong magnetic field and more than 75 known moons, including the four large Galilean moons: Io, Europa, Ganymede, and Callisto.",
        "Saturn": "Saturn is the sixth planet from the Sun and the second-largest in the Solar System, after Jupiter. Saturn is the second-largest planet in the solar system and also classified as a gas giant. It is the sixth planet from the Sun and has a diameter of about 116,460 kilometers (72,366 miles). Saturn is known for its extensive ring system, composed of ice particles and rocky debris. Its atmosphere, like Jupiter's, is primarily hydrogen and helium, with traces of methane and ammonia. Saturn has a unique hexagonal storm pattern at its north pole. It has more than 80 known moons, with Titan being the largest and notable for its thick atmosphere and hydrocarbon lakes.",
        "Uranus": "Uranus is the seventh planet from the Sun. It has the third-largest planetary radius and fourth-largest planetary mass in the Solar System. Uranus is an ice giant, the seventh planet from the Sun, and the third-largest in the solar system. It has a diameter of about 50,724 kilometers (31,518 miles). Uranus is unique among the planets because it rotates on its side, likely due to a past collision. Its atmosphere is primarily hydrogen and helium, with traces of methane that give it a blue-green color. Uranus has faint rings and a system of moons, the largest of which are Titania and Oberon.",
        "Neptune": "Neptune is the eighth and farthest known planet from the Sun in the Solar System. Neptune is the farthest planet from the Sun and the fourth-largest in the solar system. It has a diameter of about 49,244 kilometers (30,598 miles). Neptune's atmosphere is similar to Uranus, primarily hydrogen and helium, with traces of methane that give it a blue color. It has the fastest winds in the solar system, reaching speeds of up to 2,100 kilometers per hour (1,300 miles per hour). Neptune has a faint ring system and a set of moons, the largest being Triton, which is notable for its retrograde orbit and geysers of nitrogen gas erupting from its surface."
    }
    description = descriptions.get(planet_name, "Description not available")
    popup = tk.Toplevel()
    popup.geometry("300x300")
    popup.title(planet_name + " Description")
    label = tk.Label(popup, text=description, wraplength=280, justify="left")
    label.pack(pady=10, padx=10)
    close_button = tk.Button(popup, text="Close", command=popup.destroy)
    close_button.pack(pady=5)




# Create an instance of tkinter window
win = tk.Tk()
win.title("SolarSystemInteractive")
# Define the geometry of the window
win.geometry("1280x715")
win.resizable(False, False)
frame = tk.Frame(win, width=1280, height=720)
frame.pack()
frame.place(anchor='center', relx=0.5, rely=0.5)


img = ImageTk.PhotoImage(Image.open(r"C:\SolarSystemInteractive\bg.png"))


label = tk.Label(frame, image=img, )
label.place(x=-2, y=0)

# The Sun
sun_image = ImageTk.PhotoImage(Image.open(r"C:\SolarSystemInteractive\sun.png"))
sun_color = "#d47b24"
sun_button = tk.Button(
    bg=sun_color,
    relief="flat",
    image=sun_image,
    borderwidth=0,
    command=lambda: show_description("Sun")
)
sun_button.place(x=0, y=0)

# Mercury

mercury_image = ImageTk.PhotoImage(Image.open(r"C:\SolarSystemInteractive\mercury.png"))
mercury_color = "#a4a4a4"
mercury_button = tk.Button(
    bg=mercury_color,
    relief="flat",
    image=mercury_image,
    borderwidth=0,
    command=lambda: show_description("Mercury")
)
mercury_button.place(x=229, y=0)

# Venus

Venus_image = ImageTk.PhotoImage(Image.open(r"C:\SolarSystemInteractive\venus.png"))
Venus_color = "#b77f26"
Venus_button = tk.Button(
    bg=Venus_color,
    relief="flat",
    image=Venus_image,
    borderwidth=0,
    command=lambda: show_description("Venus")
)
Venus_button.place(x=287, y=0)

# Earth

Earth_image = ImageTk.PhotoImage(Image.open(r"C:\SolarSystemInteractive\earth.png"))
Earth_color = "#677fbb"
Earth_button = tk.Button(
    bg=Earth_color,
    relief="flat",
    image=Earth_image,
    borderwidth=0,
    command=lambda: show_description("Earth")
)
Earth_button.place(x=364, y=0)

# Mars

Mars_image = ImageTk.PhotoImage(Image.open(r"C:\SolarSystemInteractive\Mars.png"))
Mars_color = "#d2754b"
Mars_button = tk.Button(
    bg=Mars_color,
    relief="flat",
    image=Mars_image,
    borderwidth=0,
    command=lambda: show_description("Mars")
)
Mars_button.place(x=446, y=0)

# Jupiter

Jupiter_image = ImageTk.PhotoImage(Image.open(r"C:\SolarSystemInteractive\Jupiter.png"))
Jupiter_color = "#d2754b"
Jupiter_button = tk.Button(
    bg=Jupiter_color,
    relief="flat",
    image=Jupiter_image,
    borderwidth=0,
    command=lambda: show_description("Jupiter")
)
Jupiter_button.place(x=580, y=0)

# Saturn

Saturn_image = ImageTk.PhotoImage(Image.open(r"C:\SolarSystemInteractive\Saturn.png"))
Saturn_color = "#d7c1b3"
Saturn_button = tk.Button(
    bg=Saturn_color,
    relief="flat",
    image=Saturn_image,
    borderwidth=0,
    command=lambda: show_description("Saturn")
)
Saturn_button.place(x=811, y=0)

# Uranus

Uranus_image = ImageTk.PhotoImage(Image.open(r"C:\SolarSystemInteractive\Uranus.png"))
Uranus_color = "#8cc3cf"
Uranus_button = tk.Button(
    bg=Uranus_color,
    relief="flat",
    image=Uranus_image,
    borderwidth=0,
    command=lambda: show_description("Uranus")
)
Uranus_button.place(x=1020, y=0)
# Neptune

Neptune_image = ImageTk.PhotoImage(Image.open(r"C:\SolarSystemInteractive\Neptune.png"))
Neptune_color = "#526388"
Neptune_button = tk.Button(
    bg=Neptune_color,
    relief="flat",
    image=Neptune_image,
    borderwidth=0,
    command=lambda: show_description("Neptune")
)
Neptune_button.place(x=1150, y=0)

win.mainloop()

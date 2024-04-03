import pyshorteners
from tkinter import *

win = Tk()
win.geometry("400x280")
win.configure(bg="light blue")

def short():
    url = entry1.get()
    s = pyshorteners.Shortener()
    short_url = s.tinyurl.short(url)
    entry2.delete(0, END)
    entry2.insert(END, short_url)

Label(win, text="Enter Your Long URL Link", font="impact 17 ", bg="black", fg="white").pack(fill="x")
entry1 = Entry(win, font="10", bd=3, width=40)
entry1.pack(pady=30, padx=10)
Button(win, text="Click Here", font="impact 12", bg="black", fg="white", command=short).pack()
entry2 = Entry(win, font="impact 16", bg="light blue", width=24, bd=0)
entry2.pack(pady=25)

mainloop()

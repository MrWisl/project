import tkinter
import random
print('напишите "п" если вы на ПК,если на телефоне "т"')
device = input()
master = tkinter.Tk()
master.title('кружочки :D')
canvas = tkinter.Canvas(master, bg='blue', height=600, width=600)
canvas.pack()
def draw(event):
    x = random.randint(0,500)
    y = random.randint(0,500)
    b = random.randint(100,1000)
    oval = canvas.create_oval((100,100), (b,b), fill='red')
    canvas.move(oval,x,y)   
    return
if device == 'т':
    btn = tkinter.Button(master,text='Тапаем',
                     command=draw
                     )
    btn.pack()
    master.bind("<ButtonPress>", draw)
elif device == 'п':   
    master.bind("<KeyPress>", draw)

master.mainloop()

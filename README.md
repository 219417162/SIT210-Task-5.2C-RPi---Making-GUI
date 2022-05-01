# SIT210-Task-5.2C-RPi---Making-GUI
Import time

import tkinter

import RPi.GPIO as GPIO


kar = tkinter.Tk()


kar.title("STOP STOP STOP")
kar.geometry("500x300")
kar.configure(background = "white")


GPIO.setmode(GPIO.BCM)
GPIO.setwarnings(False)


redlight = 25


yellowlight = 23


greenlight = 14


GPIO.setup(redlight, GPIO.OUT)


GPIO.setup(yellowlight, GPIO.OUT)


GPIO.setup(greenlight, GPIO.OUT)




def fun(): #Red
    GPIO.output(greenlight, 0)
    GPIO.output(yellowlight, 0)
    GPIO.output(redlight, 1)


def fun1(): #Yellow
    GPIO.output(redlight, 0)
    GPIO.output(yellowlight, 1)
    GPIO.output(greenlight, 0)


def fun2(): #Green
    GPIO.output(yellowlight, 0)
    GPIO.output(greenlight, 1)
    GPIO.output(redlight, 0)












k = tkinter.Label(kar, text="START ", bg = "white", fg = "black" )
p = tkinter.Label(kar, text="SLOW", bg = "white", fg = "black" )
v = tkinter.Label(kar, text="REACH", bg = "white", fg = "black" )


s = tkinter.Label(kar, bg = "green")


X = tkinter.Label(kar, bg = "green")
    
msg = tkinter.Button(kar, text = "STOP", bg = "red", command=fun)


X1 = tkinter.Label(kar, bg = "sky blue")


msgA = tkinter.Button(kar, text = "WAIT", bg = "Yellow", command=fun1)


X2 = tkinter.Label(kar, bg = "sky blue")


msgB = tkinter.Button(kar, text = "LEAVE", bg = "green", command=fun2)




k.pack()
p.pack()
v.pack()
s.pack()
msg.pack()
X.pack()
msgA.pack()
X1.pack()
msgB.pack()
X2.pack()


kar.mainloop()

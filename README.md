# Calculator
import tkinter
from tkinter import *


root = Tk()
root.geometry('303x467')
root.title("Aakash's Calculator")
e = Entry(root, width=25,font=("Callibary",15) ,bg="light grey" ,borderwidth=10)
e.grid(row=0, column=0, columnspan=10)

def btn_click(number):
    c = e.get()
    e.delete(0,END)
    e.insert(0,str(c)+str(number))

def clear():
    return e.delete(0, END)

def add():
    first_number = e.get()
    global f_num
    global math
    math = "addition"
    f_num = int(first_number)
    e.delete(0,END)


def subtract():
    first_number1 = e.get()
    global f_num
    global math
    math = "subtraction"
    f_num = int(first_number1)
    e.delete(0,END)


def multiply():
    first_number1 = e.get()
    global f_num
    global math
    math = "multiplication"
    f_num = int(first_number1)
    e.delete(0,END)

def divide():
    first_number1 = e.get()
    global f_num
    global math
    math = "division"
    f_num = int(first_number1)
    e.delete(0,END)

def sqr_root():
    first_number1 = e.get()
    global f_num
    global math
    math = "sqr root"
    f_num = int(first_number1)
    e.delete(0,END)
    e.insert(0,f_num**(1/2))




def equal():
    try:
        second_number = e.get()
        e.delete(0,END)
        if math=="addition" :
            e.insert(0,f_num + int(second_number))
    
        elif math=="subtraction" :
            e.insert(0,f_num - int(second_number))

        elif math=="multiplication" :
            e.insert(0,f_num * int(second_number))
    
        elif math=="division":
            e.insert(0,f_num / int(second_number))

    except:
        e.insert(0,"cannot divide by 0")

#-------------CREATING BUTTONS----------------------

btn1 = Button(root, text="1",font=("callibary",11, "bold"), padx=40, pady=20, command= lambda:btn_click(1))
btn2 = Button(root, text="2",font=("callibary",11, "bold"), padx=40, pady=20, command= lambda:btn_click(2))
btn3 = Button(root, text="3",font=("callibary",11, "bold"), padx=40, pady=20, command= lambda:btn_click(3))
btn4 = Button(root, text="4",font=("callibary",11, "bold"), padx=40, pady=20, command= lambda:btn_click(4))
btn5 = Button(root, text="5",font=("callibary",11, "bold"), padx=40, pady=20, command= lambda:btn_click(5))
btn6 = Button(root, text="6",font=("callibary",11, "bold"), padx=40, pady=20, command= lambda:btn_click(6))
btn7 = Button(root, text="7",font=("callibary",11, "bold"), padx=40, pady=20, command= lambda:btn_click(7))
btn8 = Button(root, text="8",font=("callibary",11, "bold"), padx=40, pady=20, command= lambda:btn_click(8))
btn9 = Button(root, text="9",font=("callibary",11, "bold"), padx=40, pady=20, command= lambda:btn_click(9))
btn0 = Button(root, text="0",font=("callibary",11, "bold"), padx=40, pady=20, command= lambda:btn_click(0))
btn_clear = Button(root,text="clear", font=("callibary",11, "bold"),padx=26, pady=20, command= clear)
btn_add = Button(root, text="+",font=("callibary",11, "bold"), padx=40, pady=20,command=add )
btn_subtract = Button(root, text="-",font=("callibary",11, "bold"), padx=42, pady=20, command=subtract)
btn_multiply = Button(root, text="*",font=("callibary",11, "bold"), padx=40, pady=20, command=multiply )
btn_divide = Button(root, text="/",font=("callibary",11, "bold"), padx=42, pady=20, command=divide )
btn_sqr_root = Button(root, text="sqr root",font=("callibary",11, "bold"), padx=16, pady=20, command=sqr_root )

btn_equal = Button(root, text="=",font=("times new roman",12,"bold") ,padx=39, pady=20, command=equal)
btn1.grid(row=3, column=0)
btn2.grid(row=3, column=1)
btn3.grid(row=3, column=2)

btn4.grid(row=2, column=0)
btn5.grid(row=2, column=1)
btn6.grid(row=2, column=2)

btn7.grid(row=1,column=0)
btn8.grid(row=1,column=1)
btn9.grid(row=1,column=2)

btn0.grid(row=4, column=0)
btn_clear.grid(row=4, column=1, columnspan=1)
btn_add.grid(row=4, column=2)
btn_subtract.grid(row=5, column=0)
btn_multiply.grid(row=5,column=1)
btn_divide.grid(row=5, column=2)
btn_equal.grid(row=6, column=1,columnspan=1)
btn_sqr_root.grid(row=6,column=0)


root.mainloop()

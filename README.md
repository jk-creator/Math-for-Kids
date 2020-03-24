# Math-for-Kids
This is a small Python application(with gui) for children's simple Mathematical expressions.

import tkinter as tk
from functools import partial
from tkinter import *
from tkinter import ttk
root = Tk()
root.title('Maths for kids')


def close():
    root.destroy()
    return


def top_text():
    def closer():
        root.destroy()
        return

    ttext = Label(root, text="What's your calculation?")
    ttext. grid(row=0, column=1)
    start.destroy()  # destroys the button start after displaying text
    close.destroy()  # destroys close button
    close2 = Button(root, text="Close", command=closer)
    close2.grid(row=9, column=0)
    root.minsize(250, 120)  # changes the size of the window
    lb_1 = ttk.Label(root, text="Enter value 1:")
    lb_1.grid(row=1, column=0)
    val1 = tk.StringVar()  # creates a var that takes string type
    val2 = tk.StringVar()  # creates a var that takes INT type
    val_1 = ttk.Entry(root, width=25, textvariable=val1)  # assigns val1 a specific tkinter object
    val_1.grid(row=1, column=1)
    # v1 = (val1.get())
    print(val1)
    lb_2 = ttk.Label(root, text="Enter value 2:")
    lb_2.grid(row=2, column=0)
    val_2 = ttk.Entry(root, width=25, textvariable=val2)  # assigns val1 a specific tkinter object
    val_2.grid(row=2, column=1)
    # v2 = (val2.get())
    labelresult = tk.Label(root)
    labelresult.grid(row=23, column=90)

    def res_try(label_r, n1, n2):
        n1 = n1.get()
        n2 = n2.get()
        r_add = int(n1) + int(n2)
        # r_mult = int(n1) * int(n2)
        # r_div = int(n1) / int(n2)
        # n1sq = int(n1) ** 2
        # n2sq = int(n2) ** 2
        label_r.config(text="Res = %d" % r_add)
        return
    res_try = partial(res_try, labelresult, val1, val2)
    tk.Button(root, text="Add", command=res_try).grid(row=4, column=2)

    # print(val2)
    # print(v1, v2)
    # r1 = Operations(v1, v2)
    # r1.addNumbers()
    # r1.minN()
    # r1.multN()


start = Button(root, text="Start", command=top_text)
start.grid(row=0, column=1)
close = Button(root, text="Close", command=close)
close.grid(row=1, column=1)
root.mainloop()
# The name mazpartial originates from the use of the partial function from functools package.
# The original project was named Mazematic.
# Credits JKCUP

from tkinter import *
from tkinter.ttk import*

def cal():
    a=float(Entry.get(input))
    b=float(Entry.get(input1))
    c=float(Entry.get(input2))
    x=Combobox.get(combo)
    y=Combobox.get(combo1)
    z=Combobox.get(combo2)
    if x=="Inch":
        a=a/12
    elif x=="Milimeter":
        a=a/304.8
    if y=="Inch":
        b=b/12
    elif y=="Milimeter":
        b=b/304.8
    if z=="Inch":
        c=c/12
    elif z=="Milimeter":
        c=c/304.8
    vol=a*b*c
    Entry.insert(output,0,vol)


def clear():
    Entry.delete(output,0, 'end')

window = Tk()
window.geometry("500x350")
window.resizable(0,0)
window.title("Volume Calculator")
#creating frame1
f1=Frame(window,width=500,height=50)
f1.grid(row=0,column=0)
f1.pack(side=TOP)
icon=PhotoImage(file = "C:/Users/royla/Desktop/Capture.png" )
label=Label(f1,image=icon)
label.pack()
#creating frame2
f2=Frame(window,width=500,height=300)
f2.pack()
#creating entries
l1=Label(f2,text="Volume",font=("Calibri",20))
l1.grid(column=1,row=0)
output=Entry(f2,width=30)
output.grid(column=1,row=1)
b1=Button(f2,text='Clear',command=clear)
b1.grid(column=2,row=1)

s=Label(f2,text=" ")
s.grid()

l2=Label(f2,text="Enter Length")
l2.grid(column=0,row=3)
combo=Combobox(f2)
combo['values']=("Feet","Inch","Milimeter")
combo.grid(column=1,row=3)
combo.current(0)
input=Entry(f2,width=20)
input.grid(column=2,row=3)

s1=Label(f2,text=" ")
s1.grid()

l3=Label(f2,text="Enter section height")
l3.grid(column=0,row=5)
combo1=Combobox(f2)
combo1['values']=("Feet","Inch","Milimeter")
combo1.grid(column=1,row=5)
combo1.current(0)
input1=Entry(f2,width=20)
input1.grid(column=2,row=5)

s2=Label(f2,text=" ")
s2.grid()

l3=Label(f2,text="Enter section width")
l3.grid(column=0,row=7)
combo2=Combobox(f2)
combo2['values']=("Feet","Inch","Milimeter")
combo2.grid(column=1,row=7)
combo2.current(0)
input2=Entry(f2,width=20)
input2.grid(column=2,row=7)

s3=Label(f2,text=" ")
s3.grid()
s4=Label(f2,text=" ")
s4.grid()

b=Button(f2,text="Submit",command=cal)
b.grid(column=1,row=10)


window.mainloop()

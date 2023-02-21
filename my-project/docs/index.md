# Welcome to Haces_Math_2uls


## 
    Name: Frank Aboagye



Introduction:
Realising that most Junior & Senior High Schools find difficulty, in certain maths areas like graphs, quadratics and so on, I decided to come up with an application that would help these students.

<hr>

## Available python files
There are five python file in this project

* `compiledcode.py` - Start
* `linearcalculator.py` - for the graph
* `matrices.py` - for the matrix
* `quadractics.py` - the quadratics
* `finalmessageend.py` - End 


<a href="allthepythoncodes.zip" download>Click Here To download all the python files</a>

<hr>

## PROJECT  LAYOUT
<hr>

## 1. compiledcode.py

        try:
            print("\n\t\t\t\t\t\t\t\t\t\tWelcome to Haces_Maths_2uls!\n Our Tools\t1. Linear Graphing calculator\n\t\t2. Matrices\n\t\t3. Quadratics\n\t\t4.Finish")



            choice = eval (input("Select Any: "))

            while choice!= 4:


                if choice == 1:
                    
                    from linearcalculator.py import *
                    

                elif choice == 2:
            
                    from matrices.py import *

                elif choice == 3:
                
                    from quadratics.py import *

                choice = eval(input("\n\t\t1. Linear Graphing calculator\n\t\t2. Matrices\n\t\t3. Quadratics\n\t\t4. Sequences\n\t\t5.Finish\n: ==> "))
                    
                
            from finalmessageend.py import *

        except:
            ModuleNotFoundError
            print("..........")
    
`choice` takes user input from the four options given.
There is a `while` loop that continuously asks the user to select an option.
For option 1, it initialises linear calculator, opt 2 initialises matrices, and it continues in that order. 
The `finalmessageend.py` is called when the loop terminates. 

<hr>

## 2. linearcalculator.py

        try:

            import turtle
            
            import tkinter as tk


            ask = eval(input("\n\t\t1. Commence\n\t\t2.Quit\n\t\t==>"))

            while ask == 1:

                def start():  
                    t1.color('red')
                    t1.up()   
                    t1.goto(-200,250)
                    t1.down()
                    t1.write("Welcome to Frank's linear graphing calculator! " ,False ,'center', font = ('Times new Roman', 20, 'bold'))
                    
                    
                    
                    

                def reset():
                    t1.reset()
                    t2.reset()
                    t3.reset()


                def drawaxis():
                    t1.up()
                    position = t2.position()
                    t2.down()
                    
                    for _ in range(0, 350,50):
                        t2.forward(50)
                        t2.dot()

                    t2.setposition(position)

                    for _ in range(0, 350, 50):
                        t2.backward(50)
                        t2.dot()
                    t2.up()
                    t2.goto(350,0)
                    t2.down()
                    t2.write("X-axis" ,False ,'center', font = ('Times new Roman', 15, 'italic'))
                    t2.up()
                    t2.goto(0,0)
                    

                    
                    t1.reset()
                    t1.right(90)
                    t1.up()
                    t1.goto(0,0)
                    t1.down()
                    for _ in range(0,350,50):
                        t1.forward(50)
                        t1.dot()

                    t1.goto(0,0)
                    t1.left(180)
                    
                    for _ in range(0,350,50):
                        t1.forward(50)
                        t1.dot()
                        

                    t1.up()
                    t1.goto(0,350)
                    t1.down()
                    t1.write("Y-axis" ,False ,'center', font = ('Times new Roman', 15, 'italic'))
                    t1.up()
                    t1.goto(0,0)
                    


                ##__________________________________making the interface to take values_______________________________

                master = tk.Tk()
                tk.Label(master, 
                        text="Coefficient_of_x").grid(row=0)

                tk.Label(master, 
                        text="Intercept").grid(row=1)


                e1 = tk.Entry(master)
                e2 = tk.Entry(master)


                e1.grid(row=0, column=1)
                e2.grid(row=1, column=1)






                def drawingprocess(a,b):
                    m = int(a)
                    c = int(b)
                    t2.up()
                    t2.color("red")
                    for x in range (-40,40):
                        y = (m * x) + c
                        t2.goto(x, y)
                        t2.down()

                def viewproperties():
                    import tkinter as tk
                    master = tk.Tk()
                    
                    a =int(e1.get())
                    b = int(e2.get())
                    if (a > 0):    

                        properties = "Your line is continuously \nINCREASING\n about the x and y axis"

                    elif(a<0):
                        properties = "Your line is continuously \nDECREASING\n about the x and y axis"

                    else:
                        properties = "No slope\nHorizontal line"
                    msg = tk.Message(master, text = properties)
                    msg.config(bg='lightgreen', font=('times', 24, 'italic'))
                    msg.pack()
                    tk.mainloop()

                    
                        
                        


                def enter_Values():
                    a =int(e1.get())
                    b = int(e2.get())

                    drawingprocess(a,b)





                ##_______________________________using the turtle interface with tkinter________________________
                root = tk.Tk()
                canvas = tk.Canvas(master = root, width = 1000, height = 800)
                canvas.pack()
                t1 = turtle.RawTurtle(canvas)
                t2 = turtle.RawTurtle(canvas)
                t3 = turtle.RawTurtle(canvas)


                ##_________________________________for tkinterinterfaces____________________________________
                tk.Button(master,text='Show', command=enter_Values).grid(row=3,column=0,sticky=tk.W,pady=4)        
                tk.Button(master,text='line_properties', command=viewproperties).grid(row=3,column=1,sticky=tk.W,pady=4)      

                tk.Button(master, text = "start", command = start).grid(row=4,column=0,sticky=tk.W,pady=4)
                tk.Button(master, text = "reset", command = reset).grid(row=4,column=1,sticky=tk.W,pady=4)
                tk.Button(master, text = "drawaxis", command = drawaxis).grid(row=5,column=0,sticky=tk.W,pady=4)


                ##_________________________________ending the root & master tinkter______________________________________
                root.mainloop()
                master.mainloop()
                ask = eval(input("\n\t\t1. Commence again\n\t\t2. Quit\n\t\t ==> "))
            else:
                print("Thank You for using our services")
                


        except:
            ModuleNotFoundError
            
            print("..........")


The linear calculator has three Tkinter, impemented as tk. The first and second combines with the turtle to give the graph while the third, found in the `viewproperties` basically show the property of the line.

`ask` is embedded in a for loop to keep asking the user if he or she wants to continue or quit. When quit is selected, the application ends. It does not go back to the main page `compiledcode.py`

A turtle `t1` is  created that writes and draws in the first Tkinter when the `start` and `drawaxis` button are pressed / called.

With the `show` and `viewproperties` on the second Tkinter, the turtle draws a line based on the gradient and y-intercept given.

`reset` clears the interface and waits for new values.

Note!! Before exiting all the Tkinter interfaces that appear on the screen, the `reset` has to be called / pressed.

Button Explained:

`tk.Button(master, text = "start", command = start).grid(row=4,column=0,sticky=tk.W,pady=4)` This is basically the button state that appears on the tkinter interface. `master` is the name of the Tkinter interface we are using. It terminates with the `root.mainloop()`. This also holds for the `master = tk.TK()` which terminated with the `master.mainloop()`

<hr>

## 3. matrices.py

        try:
            print("Welcome to Frank's  2 x 2 matrices world\n\n!!! you can only input a maximum of two matices")
            condition = eval(input ("\n\t\t1. * Start\n\t\t2. * Quit\n: ==>"))


                
            def matrixbox():
                m1 = []
                semicolon = ";"
                comma = ","
                rows_n_colums = input("Input row separated by a comma and colums with semi colon\n eg. 2,3;5,7\n : ")

                rows_n_colums = rows_n_colums.split(semicolon)
                firstrow = rows_n_colums[0]
                secondrow = rows_n_colums[1]

                firstrow = firstrow.split(comma)
                firstrow = firstrow[:2]
                secondrow = secondrow.split(comma)
                secondrow = secondrow[:2]
                
                
                for j in firstrow:
                    m1.append(int(j))
                for i in secondrow:
                    m1.append(int(i))
                return (m1)
                




            def determinant(n):
                majorDiagonal = n[0] * n[3]
                minorDiagonal = n[1] * n[2]
                det = majorDiagonal - minorDiagonal
                return det
                





            while condition == 1:
                finalmatrix = []
                hold1 = eval(input("\n1. Addition of a matrix\n2. Subtraction of a matrix\n3. Multiplication of a matrix\n4. determinant\n: ==>"))
                if hold1 == 1:
                    firstmatrix = matrixbox()
                    secondmatrix = matrixbox()
                    for i in range(4):
                        finalmatrix.append(firstmatrix[i] + secondmatrix[i])
                    ask = eval(input("\n1. Print out final matrix\n2. Print out the final matrix and its determinant\n: ==>"))
                    if ask == 1:
                        print("\t1st row ==>  %f\t\t%f\n\t2nd row ==>  %f\t\t%f" %(finalmatrix[0],finalmatrix[1],finalmatrix[2],finalmatrix[3]))
                    elif ask == 2:
                        print("\t1st row ==>  %f\t\t%f\n\t2nd row ==>  %f\t\t%f" %(finalmatrix[0],finalmatrix[1],finalmatrix[2],finalmatrix[3]))
                        thedeterminant = determinant(finalmatrix)
                        print("\nThe determinant is : ==> " + str(thedeterminant))

                    
                elif hold1 == 2:
                    firstmatrix = matrixbox()
                    secondmatrix = matrixbox()
                    for i in range(4):
                        finalmatrix.append(firstmatrix[i] - secondmatrix[i])
                    ask = eval(input("\n1. Print out final matrix\n2. Print out the final matrix and its determinant\n: ==>"))
                    if ask == 1:
                        print("\t1st row ==>  %f\t\t%f\n\t2nd row ==>  %f\t\t%f" %(finalmatrix[0],finalmatrix[1],finalmatrix[2],finalmatrix[3]))
                    elif ask == 2:
                        print("\t1st row ==>  %f\t\t%f\n\t2nd row ==>  %f\t\t%f" %(finalmatrix[0],finalmatrix[1],finalmatrix[2],finalmatrix[3]))
                        thedeterminant = determinant(finalmatrix)
                        print("\nThe determinant is : ==> " + str(thedeterminant))


                elif hold1 == 3:
                    ask = eval(input("\n1. Scalar Multiple\n2. Multiply two matrices\n: ==> "))

                    if ask == 1:
                        firstmatrix = matrixbox()
                        factor = eval(input("Input the scalar\n: ==> "))
                        for i in range(4):
                            finalmatrix.append(factor * firstmatrix[i])
                        print(" Result\n")
                        print("\t1st row ==>  %f\t\t%f\n\t2nd row ==>  %f\t\t%f" %(finalmatrix[0],finalmatrix[1],finalmatrix[2],finalmatrix[3]))

                    elif ask == 2:
                        firstmatrix = matrixbox()
                        secondmatrix = matrixbox()
                        finalmatrix.append((firstmatrix[0] * secondmatrix[0]) + (firstmatrix[1] * secondmatrix[2]))
                        finalmatrix.append((firstmatrix[0] * secondmatrix[1]) + (firstmatrix[1] * secondmatrix[3]))
                        finalmatrix.append((firstmatrix[2] * secondmatrix[0]) + (firstmatrix[3] * secondmatrix[2]))
                        finalmatrix.append((firstmatrix[2] * secondmatrix[1]) + (firstmatrix[3] * secondmatrix[3]))
                        ask1 = eval(input("\n1. Print out final matrix\n2. Print out the final matrix and its determinant\n: ==>"))
                        if ask1 == 1:
                            print("\t1st row ==>  %f\t\t%f\n\t2nd row ==>  %f\t\t%f" %(finalmatrix[0],finalmatrix[1],finalmatrix[2],finalmatrix[3]))
                        elif ask1 == 2:
                            print("\t1st row ==>  %f\t\t%f\n\t2nd row ==>  %f\t\t%f" %(finalmatrix[0],finalmatrix[1],finalmatrix[2],finalmatrix[3]))
                            thedeterminant = determinant(finalmatrix)
                            print("\nThe determinant is : ==> " + str(thedeterminant))

                elif hold1 == 4:
                    firstmatrix = matrixbox()
                    thedeterminant = determinant(firstmatrix)
                    print("\nThe determinant is : ==> " + str(thedeterminant))



                condition = eval(input ("\n\t\t1* Start again \n\t\t2* Quit\n: ==>"))
                
                
            else:
                print("Thank You for using our services")
                



        except:
            ModuleNotFoundError
            print("..........")


`matrixbox()` begins with an empty list `m1`.  `rows_n_colums` accept input in the form a,b;c,d where a,b,c,and d are any value. First row and second row are determined by the split method.

`determinant` access matrix from `matrixbox()` and returns the major diagonal minus the minor diagonal whish gives the determinant of the matrix.

One can as well perform either addition, subtraction, multiplication or  find the determinant of a matrix as many times as the user want to. When the `hold1` is given a value or when the user inputs a value of 4, the application end.

<hr>

## 4. quadratics.py
        try:

            import math
            ask = eval(input("\n\t\t\t>>>Welcome to frank's quadratic room\n\t1. Start\n\n\t2. Quit\n :==> "))

            def solutionofquadractic(a,b,c):
                dicrim = ( (b**2) - (4 * a * c) )
                if dicrim < 0:
                    print("\n !! The nature of the root of the quadractic equation is imaginary . Cannot compute...")

                else:
                    root1 = ((-1 * b)  +(math.sqrt( (dicrim) )) ) / (2 * a)
                    root2 = ((-1 * b)  -(math.sqrt( (dicrim) )) ) / (2 * a)
                    print("\n\n Answer:\n\tx = %f\n\n\tx = %f" %(root1, root2))

            def d_property(a,b,c):
                d_Value = ( (b**2) - (4 * a * c))

                if d_Value == 0:
                    print("\n\n\t Discriminant D = b^2 - 4ac \n\n\t D = %f^ 2 - (4 x % f x %f )\n\n\t D = 0\n\n\t Since D = 0 , the roots are REAL and EQUAL" %(b, a, c, d_Value))

                elif d_Value > 0:
                    print("\n\n\t Discriminant D = b^2 - 4ac \n\n\t D = %f^ 2 - (4 x % f x %f )\n\n\t D = %f\n\n\t Since D > 0, the roots are REAL and UN-EQUAL" %(b, a, c, d_Value))

                else :
                    print("\n\n\t Discriminant D = b^2 - 4ac \n\n\t D = %f^ 2 - (4 x % f x %d )\n\n\t D = %f\n\n\t Since D < 0, the roots are IMAGINARY (no real roots)" %(b, a, c, d_Value))


            def quadractics():
                anykey = str(input("\n\t\t Here are the two forms a quadratic equation should be written in. Please Select your format \n\n\t\t1. Standard form: ax^2+ bx + c \n\n\t\t2. Vertex form:  a(x + b)^2+ c \n\n\t\twhere a, b, c, and d are just numbers \n\n Enter any key to continue :==> "))


                coeff_x_squared = eval(input("\nEnter the co-effiecient of x squared (i.e,  a) :==> "))
                coeff_x = eval(input("Enter the co-effiecient of x (i.e,  b):==> "))
                const = eval(input("Enter the constant (i.e,  c):==> "))
                userinput = (input("\n\t\t1. Solve my quadratic equation\n\n\t\t2. View Discriminant property of the quadractic equation\n:==> "))

                if userinput == "1":
                    solutionofquadractic(coeff_x_squared , coeff_x, const)

                elif userinput == "2":
                    d_property(coeff_x_squared , coeff_x, const)

                else:
                    print("Invalid")
                    

            while ask != 2:
                quadractics()
                ask = eval(input("\n\n\t1. Continue \n\n\t2. Quit\n :==> "))        

            else:
                print("Thank You for using our services")
                
        except:
            ModuleNotFoundError
            print("..........")

The quadratics.py file has the `quadratics()` functions which provide options for the user. It has the `solutionofquadratic()`function called in it which computes the discriminant of the given matrix. `d_property` takes three inputs that prints out the nature of the roots of the determinants.
The application terminantes when the user inputs 2.

<hr>

## 5. finalmessageend.py
        print("T H A N K Y O U ")

This has been included to print a final message if some error occurs.

<hr>
<hr>
 <h3><em><strong> IMPORTANT INFORMATION</strong></em></h3>
Unexpected Errors could occur if:

1. The user input is not part of the options
2. The type of the user input does not match
3. The folders are not kept in the same directory
4. The `try` and `exception` prevents errors that might happen. Errors could show when running on other machines.
<hr>

## Tips to ensure smooth code performance
1. <em>When running the linear calculator code, make sure to always press the reset button before closing all the Tkinter interface.</em>
2. <em>The order of the functions should not be changed in the codes.</em>

<hr>

## Running the code: STEPS




1.	Run the compiledcode.py
2.	Select any of the options:
    
    a.	<em>For option 1: linear calculator</em>
    
    1.	Two options pop up. Commence and Quit.
    2.	Enter 1 
    3.	Two tkinter interface pops out.
    4.	Go to the larger one. Press the start button first. This would display a welcome message.
    5.	Next press the drawaxis button.
    6.	Move to the second tkinter interface. That is the smaller one. And enter the desired values. Press the show button.
    7.	To check line property, you can press the line_properties button.
        
        Take Note:
    
    8.	You could draw again but pressing button.
    9.	To exit, first press the reset button(crucial). Close the small tkinter interface. Close the big tkinter interface. A message pops up.
    10.	You can then start again or quit.

        
    b.	<em>For option 2: matrices</em>

    
    1.	A welcome message is displayed. Enter 1 to start.
    2.	You can now select any of the options.
    3.	For addition, subtraction and multiplication, you have to input the first matrix and press enter. Then input the second matrix.
    
        Note:
    
        The matrix format, eg. 12,5;4,9
        No spaces. First row first separated by a comma. Then a semicolon. The next row follows. You can then print the final matrix answer or the answer and its determinant.
    
    4.	You can start again or quit.


    c.  <em>For option 3: quadratics</em>

    1.	Enter 1 to start. Enter any key as the message reads.
    2.	Input the values. Choose from the two options.
    3.	You can continue or quit.


    d.<em>	For option 4: finish </em>
    
    The program ends.

<hr>

## Limitations
1. The matrix cannnot have a fraction value
2. The line drawn by the turtle has a scale of 50 unit.
And so some values would not produce a perfect line




<hr>
 <em>Frank Aboagye. Python project &copy; 2020. &reg;</em>
<hr>








        




    
        
    
    

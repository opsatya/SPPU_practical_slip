# SPPU_practical_slip

########################## SLIP 2 ####################################################

Q1.A
use https://www.tutorialspoint.com/compile_java_online.php

import java.util.Scanner;

public class VowelsInString {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String inputString = scanner.nextLine().toLowerCase(); // Convert input to lowercase for case-insensitive comparison
        scanner.close();

        System.out.print("Vowels in the given string: ");

        // Loop through each character in the input string and check if it is a vowel
        for (int i = 0; i < inputString.length(); i++) {
            char ch = inputString.charAt(i);
            // Check if the character is a vowel (a, e, i, o, u)
            if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u') {
                System.out.print(ch + " ");
            }
        }
    }
}

Q1.B
Install JDK on System run try vscode once run you will get a popup
filename: MouseEventExample.java

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class MouseEventExample {

    public static void main(String[] args) {
        JFrame frame = new JFrame("Mouse Events Example");
        JTextField textField = new JTextField(20);

        frame.setLayout(new FlowLayout());
        frame.add(textField);

        frame.addMouseListener(new MouseAdapter() {
            @Override
            public void mouseClicked(MouseEvent e) {
                textField.setText("Mouse Clicked at: X=" + e.getX() + ", Y=" + e.getY());
            }
        });

        frame.addMouseMotionListener(new MouseAdapter() {
            @Override
            public void mouseMoved(MouseEvent e) {
                textField.setText("Mouse Moved at: X=" + e.getX() + ", Y=" + e.getY());
            }
        });

        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(300, 200);
        frame.setVisible(true);
    }
}

Q2.A
python program onlinegdb

def count_case_characters(input_string):
    upper_count = 0
    lower_count = 0
    
    for char in input_string:
        if char.isupper():
            upper_count += 1
        elif char.islower():
            lower_count += 1
    
    return upper_count, lower_count

# Sample String
sample_string = 'The quick Brown Fox'

# Calculate counts
upper, lower = count_case_characters(sample_string)

# Output the result
print("No. of Upper case characters:", upper)
print("No. of Lower case characters:", lower)


Q2.B
Need vs + python installed

import tkinter as tk
from time import strftime

root = tk.Tk()
root.title("Digital Clock")

# Function to display time
def time():
    string = strftime('%H:%M:%S %p') # Format time as Hour:Minute:Second AM/PM
    label.config(text = string)
    label.after(1000, time) # Update time every 1 second

label = tk.Label(root, font = ('calibri', 40, 'bold'), background = 'black', foreground = 'cyan')
label.pack(anchor = 'center')

time()  # Initial call to display time
root.mainloop()



############## SLIP 11 #########################################

Q1.A
filename: Calculator.java
need to run a command to do use of program : java Calculator addition 10 10

public class Calculator {
    public static void main(String[] args) {
        if (args.length < 3) {
            System.out.println("Invalid input. Usage: java Calculator <operation> <num1> <num2>");
            return;
        }

        String operation = args[0];
        double num1 = Double.parseDouble(args[1]);
        double num2 = Double.parseDouble(args[2]);

        double result = 0;

        switch (operation) {
            case "1":
            case "addition":
                result = num1 + num2;
                System.out.println("Result: " + result);
                break;
            case "2":
            case "subtraction":
                result = num1 - num2;
                System.out.println("Result: " + result);
                break;
            case "3":
            case "multiplication":
                result = num1 * num2;
                System.out.println("Result: " + result);
                break;
            case "4":
            case "division":
                if (num2 != 0) {
                    result = num1 / num2;
                    System.out.println("Result: " + result);
                } else {
                    System.out.println("Error: Division by zero is not allowed.");
                }
                break;
            default:
                System.out.println("Invalid operation. Please enter 1, 2, 3, or 4 for addition, subtraction, multiplication, or division respectively.");
        }
    }
}

Q1.B
use vs + jdk
filename: TableLampApplet.java

import javax.swing.JFrame;
import javax.swing.JPanel;
import java.awt.Color;
import java.awt.Graphics;
import java.util.Random;

public class TableLampApplet extends JPanel {
    private Color lampColor;

    public TableLampApplet() {
        lampColor = Color.YELLOW; // Initial color of the lamp (you can set any color you prefer)
    }

    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        
        // Set lamp color randomly
        setRandomLampColor(g);
        
        // Draw lamp base
        g.setColor(Color.GRAY);
        g.fillRect(100, 200, 100, 20);
        
        // Draw lampshade
        g.setColor(lampColor);
        g.fillRect(110, 50, 80, 150);
    }

    private void setRandomLampColor(Graphics g) {
        // Generate random RGB values for the lamp color
        Random random = new Random();
        int red = random.nextInt(256);
        int green = random.nextInt(256);
        int blue = random.nextInt(256);

        // Set lamp color with the random RGB values
        lampColor = new Color(red, green, blue);
        g.setColor(lampColor);
    }

    public static void main(String[] args) {
        JFrame frame = new JFrame("Table Lamp App");
        TableLampApplet lampApplet = new TableLampApplet();
        frame.add(lampApplet);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(300, 300);
        frame.setVisible(true);
    }
}

Q2.A (onlinegdb)
# Original tuples
tuples = [(1, 2, 3, 4), (3, 5, 2, 1), (2, 2, 3, 1)]

# Compute element-wise sum using list comprehension
element_wise_sum = tuple(sum(x) for x in zip(*tuples))

# Output the result
print("Element-wise sum of the given tuples:", element_wise_sum)

Q2.B (onlinegdb)

import tkinter as tk
from tkinter import messagebox

def change_color(color):
    root.configure(background=color)
    messagebox.showinfo("Color Changed", f"Background color changed to {color}")

root = tk.Tk()
root.title("Color Changer")

# Menu bar
menubar = tk.Menu(root)
root.config(menu=menubar)

# Color options menu
color_menu = tk.Menu(menubar, tearoff=0)
color_menu.add_command(label="Red", command=lambda: change_color("red"))
color_menu.add_command(label="Green", command=lambda: change_color("green"))
color_menu.add_command(label="Blue", command=lambda: change_color("blue"))
color_menu.add_command(label="Yellow", command=lambda: change_color("yellow"))
color_menu.add_command(label="White", command=lambda: change_color("white"))

# Adding color menu to the menu bar
menubar.add_cascade(label="Colors", menu=color_menu)

root.mainloop()

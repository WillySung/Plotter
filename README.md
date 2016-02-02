# Plotter
>The final project of the Embedded System Course

# Component
 1. stepper motor(from old DVD players) *2
 2. servo motor *1
 3. STM32F429i-discovery *2
 
# Structure
 1. Hardware
  1.  One stepper motor be the X axis and the other be the Y
    * The first STM32 controls X and the other controls Y
  2.  Servo motor be the Z axis to let the pen up and down
    * Servo motor can be on each board 
 2. Software
  1.  The programs in two boards are basically the same except the X,Y coordinate
    * X board only has x corrdinate and Y board only has Y
    * To let two stepper motors work in synchronization, we have to compute the delay between two boards
      , which is really trouble some
  2.  Use MATLAB to read a picture, do image binarization, and create X,Y coordinate
  3.  Put the coordinate in a txt file and execute readtest.c
    * readtest.c will create output_x.txt and output_y.txt which have coordinate and delay done already
    * put the coordinate in output_x.txt in `draw()` in STM32 program and so does the other one
  4.  So , we can plot
  
# Problem
 1. Multithread : We don't know how to do it on STM32 so we use two boards
  1. we have tried FREERTOS,co-routine..
 2. The mechanism is not strong enough

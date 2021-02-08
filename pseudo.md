## Elevator program

1. SHOW: What floor would you like to go to? 
    For this we will need a user interface inside of the elevator

2. INIT: 15th floor (desired floor)
    The patron enters the desired floor
    
    Store variables for our Elevator program
    (var d = desired floor)
    (var f = current floor)

3. START: 

    IF (door is closed)
            proceed to next step
        ELSE 
            wait for door to close
    We will need to make sure that the door is closed before the elevator moves

    IF (you are below (d))
            Motor start signal: Fwd     
        ELSE 
            Motor start signal: Rev
    We will need to send the proper signal to our motor controller 

    While the elevator is running, we need to keep track of it's location. To do this
    we will need limit switches with N.O. contacts that, when closed, send a signal to
    our CPU that updates the value in our program. 

    WHILE (f < d) {
        continue running motor; f++;
    }
        ENDWHILE

    Now we need to send a stop signal to our motor controller

    IF (f = d) {
        send stop signal to motor control
    }
        ENDIF

    Once the motor has stopped, we can proceed to the next step of opening the doors. 

    



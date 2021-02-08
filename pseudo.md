## Elevator program

1. SHOW: What floor would you like to go to? 
    For this we will need a user interface inside of the elevator

2. INIT: The patron enters the desired floor
         15th floor (desired floor)
    
    Store variables for our Elevator program
    (var d = desired floor)
    (var f = current floor)

3. START: 
    
 a. We will need to make sure that the door is closed before the elevator moves. For this
    we will use proximity sensors that will send a closed or open signal to the CPU.
    
    IF (door is closed){
            proceed to next step;
            }
        ELSE {
            wait for door to close;
            }
            
 b. We will need to send the proper signal to our motor controller to engage the mechanical 
    interlocks of the forward or reverse contactors.

    IF (f < d)){
            Motor start signal: Fwd ; 
            }
        ELSE {
            Motor start signal: Rev;
            }
            

 c. While the elevator is running, we need to keep track of it's location. To do this
    we will need limit switches with N.O. contacts that, when closed, send a signal to
    our CPU that updates the value in our program. 

    let counter = f;
    WHILE (f < d) {
        continue running motor; 
        f++;
    }
        ENDWHILE

    Now we need to send a stop signal to our motor controller

    IF (f = d) {
        send stop signal to motor control;
    }
        ENDIF

    Once the motor has stopped, we can proceed to the next step of opening the doors. 
    
        IF (Motor has stopped){
            open doors;
        }
            ENDIF
            
    END
    
    The elevator will require a 60A 480v 3-phase power supply with a battery back up UPS for emergencies. 

    



## Elevator program

# Objects
- There will be a bank of 4 elevators
- The elevators will require a 60A 480v 3-phase power supply with a battery back up and deisel generator UPS for emergencies. 
- Emergency phone located inside of the car
- Key switch for emergency fire service located on the main floor and in the cars
- Smoke sensors in the elevator shaft, car and throughout the building that will trigger an emergency response
- Seismic switch ground motion detectors to detect earthquakes and initiate the emergency response
- The car doors will need proximity sensors to send an open or closed signal to the CPU.
- To keep track of the car's location, we will need limit switches with N.O. contacts that, when closed, send a signal to our CPU that updates the value in our program. (Current floor)
- We will need to send the proper signal to our motor controller to engage the mechanical interlocks of the forward or reverse contactors (Which direction does the car needs to go)
- We will need call buttons on every floor
- We will need an interface inside of the elevator to input the desired floor
- We will need a CPU to manage elevator calls, our program, and variables for program functionality


# Functionality
1. SHOW: What floor would you like to go to? (Interface display)

2. INIT: The patron enters the elevator and inputs the desired floor    
    
    Store variables for our Elevator program
    (var d = desired floor)
    (var f = current floor)

3. START: 
    
  1. We will need to make sure that the door is closed before the elevator moves. 
            
  2. Our program will need to compare values of the desired floor against the current floor and make a decision whether to go up or down. 
            
  3. While the elevator is running, we need to keep track of it's location.  

  4. What if there are multiple calls at the same time?
     1. WHILE one car is in operation and a new call is made, we will route that call to an available car
     2. IF all cars are in operation, we will use an algorithm to decide which car will take the call
        1. ex. IF car A is on the 4th floor heading up to the 15th floor and a patron on the 10th floor calls the elevator to go up, THEN the car will stop on the 10th floor to pick up that person. (write a program that will handle this logic)
        2. ex. IF however, the patron on the 10th floor wishes to go to the lobby, THEN we will check the status of the other three cars. IF one is above the 10th floor heading down, THEN that car will stop to pick up the passenger. ELSE, the next available car will take the call to pick up the passenger. (write a program that will handle this logic)
     3. IF multiple calls are made at the exact millisecond, THEN the first available car will head towards the     nearest floor to pick up the passenger. 
 
  5. Staging - We will want at least two cars staged on the main floor when possible. 
     1. IF there are two cars on the main floor, THEN the two remaining cars will wait at their final destinations
        (This will ensure faster response times to calls on mid or top floors)
     2. IF there are no cars on the main floor, THEN the next available car will go down to the lobby

  6. What about fires, earthquakes or power outages?
     1. IF there is smoke or fire in the elevator shaft or somewhere in the building, THEN the elevators will be programmed to override it's current operation and go to the lobby. The doors will not open until you push the door open button. This feature is designed to prevent the doors from opening automatically onto a floor filled with smoke or fire. 
     2. IF there is an earthquake, THEN the elevator will go to the nearest floor AND open the doors automatically
     3. IF there is a power outage, THEN power will be switched to the UPS (either battery back up or diesel generator), AND the car will be brought to the nearest floor, THEN open the doors automatically 
 

  
            
    END
    
    
    



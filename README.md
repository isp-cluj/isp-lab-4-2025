# Implement the following exercises

In this lab you will create small Java applications by using as reference an UML class diagram. Please consider following general notes before start implementing:
- toString() method when required will return a string like *ClassName{attributeName1=attributeValue1,...,attributeNamen=attributeValuen}*.
- Do not reuse (do not import) the same class in multiple exercises. **Each exercise is standalone and should be resolved in its package.** If you need a class from a previous exercise copy it (and modify it as needed) in the package of the current exercise!
**- Create any additional constructors, getters and setters needed by your unit tests.**

## Exercise 0

This exercise demonstrate concepts you will need to apply in this lab. Solution for this diagram can be found in source folder in package *isp.lab4.exercise0*.
![Exercise 1 image](docs/ex0.jpg)

**NOTE: This exercise do not require any implementation from student.**

**The following exercises model the control of a fish aquarium, step by step**

## Exercise 1
![Exercise 1 image](docs/ex1.jpg)

Given the UML class diagram above, implement the corresponding Java program.

1. Create Java class based on the diagram above. 
2. Instantiate and test created class in the provided Exercise 1 main method.
3. Create a minimal unit test for testing the behavior of the created class (i.e., you should test that changing current time reflects in toString()).


## Exercise 2
![Exercise 2 image](docs/ex2.jpg)

The automatic fish feeder is a very useful addition to any aquarium.
Our fish feeder has two operations and a maximum capacity of 14 meals.
Once the fill up operation is called, the meals attribute has to be reset to 14
and a message should be displayed in the console. The feed operation will decrease
the number of meals by 1, and will also display a proper message into the console. 

1. Create Java class based on the diagram above. 
2. Instantiate and test created class in the provided Exercise 2 main method.
3. Create minimal unit tests for the behavior of the created class: fillUp() and feed(). 

## Exercise 3 
![Exercise 3 image](docs/ex3.jpg)

Now let's assemble the two components. Each time the current time is modified
(i.e. setCurrentTime() is called), the controller checks if it's feeding time.
If it is, then it triggers the feed operation. The time is represented as a LocalTime
(see examples in the demo package).

1. Create Java classes based on the diagram above. 
2. Instantiate and test created classes in the provided Exercise 3 main method.
3. Create minimal unit tests for the behavior of the created classes 
(check if setting the time to current time triggers the feeding operation - i.e., *meals* from *FishFeeder* are decreased).


## Exercise 4
![Exercise 4 image](docs/ex4.jpg)

Extend exercise 3 and implement the aquarium's lights control.
Algae can be a real problem in any aquarium, and to much light time will boost their growth.
But if the plant don't get enough light they will die. Keep the lights on anywhere between 6 and 8 hours per day. 
You need to add 2 new attributes for: _lightOnTime_ and _lightsOffTime_.
Also add a new class called *Lights* that has a boolean attribute *isOn* and two methods *turnOn()* and *turnOff()*.
Like in the case of the previous exercise, turning the lights on/off is determined when setting the current time in the controller.

1. Update the class diagram from exercise 3 with the newly added subsystem.
   The docs directory contains the StarUML model. You can use it to modify ex3 diagram. Export it as **ex4.jpg** and add the image to **docs**.
   Make sure the image is rendered in the readme file (i.e, you placed the image in the right dir and named it correctly).
2. Create Java classes based on your new diagram.
3. Instantiate and test created classes in the provided Exercise 4 main method.
4. Create minimal unit tests for the new behavior.

## Exercise 5 
![Exercise 5 image](docs/ex5.jpg)

The water temperature is not very important for the majority of the plants, but it is for the fish.
For tropical fish species somewhere between 24 and 27°C is recommended.
We also want a leak detection subsystem.

1. Create Java classes based on the diagram above.
   - the controller checks the water level; if it's below the preset value it turns on the alarm.
   - the controller checks the temperature; if it's below the preset value it turns on the heater;
   if the temperature equals the preset value, it turns the heater off.
2. Instantiate and test created classes in the provided Exercise 5 main method.
3. Create minimal unit tests for the new behavior (i.e., for each type of sensor check all scenarios; verify that the value of boolean *isOn* from *Actuator* is changing accordingly).

The values provided by the level and the temperature sensors have different types (int and float).
That is why the association uses the concrete implementation (i.e., in *AquariumController* you will have _LevelSensor_ and _TemperatureSensor_ attributes).
In the case of the _Actuator_-s, they can be treated the same - the association is done through the base class (i.e., in *AquariumController* you will have 2 _Actuator_ attributes).

## Exercise 6 
![Exercise 6 image](docs/ex6.jpg)

Modify exercise 5 and add pH monitoring/control.
Determine if it's possible to change the water pH without killing the fish.
If it can be done implement the control. If not, only raise an alarm.

1. Create the new class diagram. Export the diagram as **ex6.jpg** and place it in **docs** dir.
2. Implement the code and the unit tests accordingly. 


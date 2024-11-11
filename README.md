# Ex-04 Single server with infinite capacity (M/M/1):(oo/FIFO)
# DATE: 05.10.2024
## Aim :
To find (a) average number of materials in the system (b) average number of materials in the conveyor (c) waiting time of each material in the system (d) waiting time of each material in the conveyor, if the arrival  of materials follow poisson process with the mean interval time 12 seconds, serivice time of lathe machine follows exponential distribution with mean serice time 1 second and average service time of robot is 7seconds.

## Software required :
Visual components and Python

## Theory:
Queuing are the most frequently encountered problems in everyday life. For example, queue at a cafeteria, library, bank, etc. Common to all of these cases are the arrivals of objects requiring service and the attendant delays when the service mechanism is busy. Waiting lines cannot be eliminated completely, but suitable techniques can be used to reduce the waiting time of an object in the system. A long waiting line may result in loss of customers to an organization. Waiting time can be reduced by providing additional service facilities, but it may result in an increase in the idle time of the service mechanism.

![image](1.png)

This is a queuing model in which the arrival is Marcovian and departure distribution is also Marcovian,number of server is one and size of the queue is also Marcovian,no.of server is one and size of the queue is infinite and service discipline is 1st come 1st serve(FCFS) and the calling source is also finite.

## Procedure :

![imAGE](2.png)



## Experiment:


 
## Program
```py
arr_time = float(input("Enter the mean inter-arrival time of objects from Feeder (in secs): "))
ser_time = float(input("Enter the mean inter-service time of Lathe Machine (in secs): "))
Robot_time = float(input("Enter the additional time taken for the Robot (in secs): "))

lam = 1 / arr_time
mu = 1 / (ser_time + Robot_time)

print("-------------------------------------------------------")
print("Single Server with Infinite Capacity (M/M/1): (oo/FIFO)")
print("-------------------------------------------------------")
print("The mean arrival rate per second: %0.2f" % lam)
print("The mean service rate per second: %0.2f" % mu)

if lam < mu:
    Ls = lam / (mu - lam)
    Lq = Ls - lam / mu
    Ws = Ls / lam
    Wq = Lq / lam

    print("Average number of objects in the system: %0.2f" % Ls)
    print("Average number of objects in the conveyor: %0.2f" % Lq)
    print("Average waiting time of an object in the system: %0.2f secs" % Ws)
    print("Average waiting time of an object in the conveyor: %0.2f secs" % Wq)
    print("Probability that the system is busy: %0.2f" % (lam / mu))
    print("Probability that the system is empty: %0.2f" % (1 - lam / mu))
else:
    print("Warning! Overflow will happen in the conveyor.")
print("--------------------------------------------------")

```

## Output :
![Screenshot 2024-11-10 181320](https://github.com/user-attachments/assets/50835bbc-7595-4a73-8e6d-c98ffdd6ccee)



## Result :
Thus the experiment is executed successfully.

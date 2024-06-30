# Deadlock-Avoidance-Detection-
##Description:
This C++ program implements the Banker's Algorithm, which is a resource allocation and deadlock avoidance algorithm. The algorithm checks whether the system is in a safe state by simulating the allocation of resources to processes.

Code Explanation:
1.Constants:

const int P = 5;: Number of processes.
const int R = 3;: Number of resources.

2.Function Definitions:
 calculateNeed:

   Parameters: int need[P][R], int maxm[P][R], int allot[P][R].
   Purpose: Calculates the need matrix for each process.
   Explanation: The need for a resource is calculated as the maximum resource required minus the allocated resource for each process.

isSafe:

Parameters: int processes[], int avail[], int maxm[][R], int allot[][R].
Purpose: Checks if the system is in a safe state.
Explanation:
Calculate the need matrix by calling calculateNeed.
Initialize the finish array to mark processes as unfinished.
Create a work array to keep track of available resources.
Try to find a process that can be completed with the current available resources.
If such a process is found, mark it as finished and add its allocated resources to the work array.
Repeat until all processes are finished or no further processes can be finished.
If all processes can be finished, print the safe sequence and return true; otherwise, print that the system is not in a safe state and return false.

3.Main Function:

Initialize the processes, available resources, maximum resources, and allocated resources.
Call the isSafe function to check if the system is in a safe state.

4.Detailed Explanation of Execution
Initialize Process and Resource Details:

        processes[]: Array of process IDs.
        avail[]: Array of available instances of each resource type.
        maxm[][]: Matrix representing the maximum demand of each process for each resource.
        allot[][]: Matrix representing the currently allocated resources for each process.
Calculate Need Matrix:

        Call calculateNeed to determine the remaining resource needs for each process.
Check Safe State:

        Initialize the finish array to mark all processes as unfinished.
        Create a work array to represent currently available resources.
        Attempt to find a safe sequence of process execution where no process will wait indefinitely for resources.
        If such a sequence is found, print the safe sequence. If not, indicate that the system is not in a safe state.
Print Results:

The program prints whether the system is in a safe state and, if so, the safe sequence of process execution.
This implementation of the Banker's Algorithm ensures that the system avoids deadlock by checking if a safe sequence of process execution exists given the current resource allocation.

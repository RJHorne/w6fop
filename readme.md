# Workshop 6

For each section you should put code in the corresponding python file. 
I have also attached images of the effective state machines for each part if that helps you understand the flow of each task.


## Part 1: Geological Sampling (Lists)


The Rover has a robotic arm to collect rocks. We need a way to store these samples in memory using **Lists**.

#### Task 1.1: The Storage Bay

1.  Create a list variable called `sample_bay` containing the following initial strings: `"Basalt"`, `"Silica"`, `"Iron"`, `"Dust"`.
    
2.  Print the **first** item in the list using index `0`.
    
3.  Print the **last** item in the list using `len()` or negative indexing.
    
4.  Print the total number of samples currently in the bay.
    

#### Task 1.2: Analyzing Samples (Iteration)

We need to transmit the list of samples back to Earth.

1.  Write a `for` loop that iterates through `sample_bay`.
    
2.  Inside the loop, print the phrase: `"Transmitting data for: [Sample Name]"`.
    
    -   _Tip:_ Do not use a counter variable (like `i = 0`). Iterate directly over the items.
        

#### Task 1.3: Collection Duty (Appending)

The Rover has found new rocks.

1.  Create an empty list called `new_findings`.
    
2.  Write a loop that asks the user to `input()` a rock type **3 times**.
    
3.  Append each input to the `new_findings` list.
    
4.  After the loop, print the full list of `new_findings`.
    

#### Task 1.4: Jettisoning Waste (Extension)

The "Dust" sample is useless.

1.  Check if `"Dust"` is in your `sample_bay` list.
    
2.  If it is, remove it from the list (Hint: Look up the `.remove()` or `.pop()` method, or create a new list without it).
    
3.  Print the cleaned list to confirm "Dust" is gone.


## Part 2: Rover Telemetry (Dictionaries)

Lists are great for items, but we need to label our data (e.g., Battery Level, Temperature). For this, we use **Dictionaries**.

#### Task 2.1: System Status

1.  Create a dictionary called `rover_status` with the following keys and values:
    
    -   `"Battery"`: `100` (Integer)
        
    -   `"Heater"`: `"Off"` (String)
        
    -   `"Camera"`: `"Standby"` (String)
        
2.  Print the current status of the **Battery** by accessing its key.
    

#### Task 2.2: Status Update

The rover is moving, and conditions are changing.

1.  Update the `"Battery"` value to `85`.
    
2.  Update the `"Heater"` value to `"On"`.
    
3.  Add a **new** key-value pair to the dictionary: `"Speed"`: `5`.
    
4.  Print the entire dictionary to verify the changes.
    

#### Task 2.3: The Science Log (Nesting)

We need to store complex data about the specific sites we visit.

1.  Create a list called `mission_log`.
    
2.  Inside this list, store **two dictionaries** representing different sites.
    
    -   Dictionary 1: `{"Site": "Crater A", "Radiation": "Low", "Water": False}`
        
    -   Dictionary 2: `{"Site": "Dune B", "Radiation": "High", "Water": True}`
        
3.  **Challenge:** Write a loop that iterates through `mission_log`. For each site, print:
    
    `"Site [Name] has [Level] radiation."`.

## Part 3: Signal Integrity (Exceptions)

Signals from Mars take 20 minutes to reach Earth. If the rover crashes due to a bad input, the mission is over. We must use `try` and `except` to handle errors.

#### Task 3.1: The Motor Controller

The motor expects an integer for speed (0-100). Solar flares sometimes turn the signal into text (e.g., "Fast").

1.  Write a program that asks the user: `"Enter Motor Speed:"`.
    
2.  Wrap the input logic in a `try...except` block.
    
3.  **Try:** Convert the input to an `int` and print `"Speed set to [X]"`.
    
4.  **Except:** Catch the `ValueError` and print `"Error: Corrupted Signal. Maintaining current speed."`.
    
    +1
    

#### Task 3.2: The Persistent Receiver

The rover cannot proceed until it gets a valid coordinate.

1.  Create a function called `get_coordinate()`.
    
2.  Inside, use a `while True` loop.
    
3.  Ask the user for an X-coordinate (integer).
    
4.  If the input is valid, `break` the loop and return the number.
    
5.  If the input is invalid (String), print `"Invalid coordinate"` and let the loop repeat.
    
6.  Call the function to test it.
    

#### Task 3.3: Range Checks (Logical Errors)

Even if the input is a number, it might be dangerous (e.g., Speed 9000).

1.  Modify your code from Task 3.2.
    
2.  After successfully converting the integer, add an `if` statement.
    
3.  If the number is greater than 100 or less than -100, print `"Coordinate out of range"` and **do not break the loop**.
    
4.  Only `break` if the number is an integer **AND** within the safe range.

## Part 4: The Automated Navigation System


**Scenario:** You need to implement the main navigation logic for the Rover. It must read a sensor value (Slope Angle), validate it, check for danger (tipping over), and log the data.

#### The Logic Diagram

Translate the following logic into Python code.

1.  **START**
    
2.  **INITIALIZE:** Create an empty list `travel_log`.
    
3.  **LOOP:** Start a continuous loop (`while True`).
    
4.  **INPUT:** Ask user `"Sensor Reading (Slope Angle):"`.
    
5.  **VALIDATION (Try/Except):**
    
    -   Is it a Number?
        
    -   **NO:** Print `"Sensor Glitch"` --> Restart Loop.
        
    -   **YES:** Continue.
        
6.  **SAFETY CHECK (If/Else):**
    
    -   Is Angle > 45?
        
    -   **YES:** Print `"CRITICAL TILT! HALTING."` --> **STOP LOOP** (`break`).
        
    -   **NO:** Continue.
        
7.  **LOGGING:** Add Angle to `travel_log`.
    
8.  **OUTPUT:** Print `"Path Stable. Moving forward."`.
    
9.  **REPEAT:** Go back to Step 4.
    

#### Task 4.1: Implementation

Write the code for the diagram above. Ensure you use:

-   `while True` for the loop.
    
-   `try/except ValueError` for step 5.
    
-   `break` for the critical tilt in step 6.
    
-   `.append()` for the logging in step 7.
    

#### Task 4.2: Mission Report

After the loop breaks (the rover halts), add code to print a summary:

1.  Print `"Mission Terminated."`.
    
2.  Print `"Total steps taken:"` followed by the length (`len`) of `travel_log`.
    
3.  Print the full `travel_log` list.

### Part 5: Final Challenge - "Rover OS"

**Time Allocation:** Remaining Time

Combine everything you have learned (Lists, Dicts, Loops, Exceptions) into one menu-driven program.

**Requirements:**

1.  Initialize a **Dictionary** for status: `{"Power": 100, "Samples": 0}`.
    
2.  Initialize a **List** for storage: `inventory = []`.
    
3.  Run a `while True` loop that prints a menu:
    
    -   1.  Dig for Sample
            
    -   2.  Report Status
            
    -   3.  Emergency Stop
            
4.  **Logic:**
    
    -   **Option 1:** Ask for sample name. Add it to `inventory`. Decrease `"Power"` in the dictionary by 10.
        
    -   **Option 2:** Print the dictionary and the inventory list.
        
    -   **Option 3:** Break the loop.
        
    -   **Error Handling:** If the user enters a menu option that isn't 1, 2, or 3, catch the error (or use `else`) and warn them.

## Challenge Part

**Scenario:** Because we know signal delay between Earth and Mars is 20 minutes, we cannot control the rover in real-time. Instead, we send a **batch** of commands in a single transmission.

However, solar radiation often corrupts these transmissions. Your job is to build a processor that takes a list of raw commands, filters out the corrupted ones using `try/except`, and executes the valid ones to update the rover's position.

**The "Corrupted" Data:** Copy this list into your code:


```python
command_batch = [
    "MOVE 10",
    "TURN LEFT",
    "MOVE 5",
    "MOVE five",    # Corrupted: 'five' is text, not a number
    "DIG",
    "MOVE 20",
    "XÆA-12",       # Corrupted: Unknown command
    "RETURN",
    "MOVE 15"
]

```

**Task Requirements:**

1.  **Initialize State:** Create a dictionary to track the Rover's position: `rover_state = {"x": 0, "y": 0, "samples": 0}`
    
2.  **Process the Batch:** Write a `for` loop that iterates through `command_batch`.
    
3.  **Parse and Validate (The Hard Part):** Inside the loop, you must process each command string.
    
    -   **Step A:** Split the string into parts (e.g., `"MOVE 10"` becomes `["MOVE", "10"]`). _Hint: Use `.split()`._
        
    -   **Step B:** Check the first word (the action):
        
        -   **If "MOVE":** You need to update the `"y"` coordinate in your dictionary.
            
            -   _Constraint:_ You must use a `try...except` block here. Try to convert the second part of the string (e.g., `"10"`) into an integer.
                
            -   _Success:_ Add that number to `"y"`.
                
            -   _Failure:_ If it fails (like `"MOVE five"`), print `"Error: Invalid distance ignored"` and continue to the next command.
                
        -   **If "DIG":** Increment the `"samples"` value in your dictionary by 1.
            
        -   **If "TURN":** Print `"Turning..."` (No state change needed for this task).
            
        -   **Anything Else:** If the command is unknown (like `"XÆA-12"`), print `"Error: Unknown command sequence"`.
            
4.  **Final Report:** After the loop finishes, print the final `rover_state` dictionary.
    
    -   _Expected Result:_ `{'x': 0, 'y': 50, 'samples': 1}` (Note: The "MOVE five" and "XÆA-12" should be ignored).
        

**Hint:** Remember that `.split()` creates a list. If you have `parts = cmd.split()`, then `parts[0]` is the action ("MOVE") and `parts[1]` is the value ("10"). Be careful—commands like "DIG" might not have a `parts[1]`, so checking the length of the list first is good practice!

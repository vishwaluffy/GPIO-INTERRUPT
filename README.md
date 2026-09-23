# GPIO-INTERRUPT
Combine a GPIO interrupt with a timer-based delay to implement non-blocking switch debouncing. Examine how the method eliminates false triggering without blocking the main loop.
## Apparatus Required

| S. No. | Apparatus / Software | Specification |
|:---:|---|---|
| 1 | Microcontroller Development Board | **NXP S32K144 Development Board** |
| 2 | IDE | **S32 Design Studio** |
| 3 | Programming Language | **Embedded C** |
| 4 | SDK | **S32K144 SDK** |
| 5 | LED | On-board LED / External LED |
| 6 | Programmer / Debugger | On-board Debugger / OpenSDA |
| 7 | USB Cable | For programming and power supply |

---
## Procedure

1. Connect the **NXP S32K Evaluation Board** to the computer using the **USB Debug Cable**.

2. Open the **ANCIT GenX Tool** and create/open the project for the target S32K microcontroller.

3. Configure the **on-board user switch** as a **GPIO Digital Input**.

4. Configure the **on-board LED** as a **GPIO Digital Output**.

5. Select the appropriate switch and LED pins according to the evaluation board, such as **PTC12/PTA4** for the switch and **PTD0/PTD15** for the LED.

6. Configure the switch with the required **Active High / Active Low** logic based on the hardware configuration.

7. Enable **software debouncing through ECUx** in the ANCIT GenX configuration.

8. Configure the required **MCAL GPIO module** and generate the GPIO configuration and initialization code using the **ANCIT GenX Tool**.

9. Integrate the generated GPIO configuration and initialization files into the application project.

10. Build the project and verify that there are no compilation errors.

11. Program the generated application into the **S32K Evaluation Board**.

12. Run the application on the microcontroller.

13. Configure the application to periodically sample the switch state using **scheduler-based input monitoring**.

14. Read the debounced switch state and determine whether the switch is pressed or released.

15. Control the LED according to the switch state:
    - When the switch is pressed, turn the LED **ON**.
    - When the switch is released, turn the LED **OFF**.

16. Press and release the switch repeatedly and observe the LED response.

17. Verify that a single switch press or release produces only one valid LED state change, even though mechanical contact bounce may generate multiple HIGH/LOW transitions.

18. Confirm that the **software debounce mechanism** filters the unwanted transient transitions caused by switch bounce.

19. Verify that the LED responds correctly only to valid and stable switch press/release events without false triggering.

20. Record the observed switch states and corresponding LED states to verify the operation of the debounce mechanism.

---




## LOGIC
<img width="463" height="266" alt="image" src="https://github.com/user-attachments/assets/b16bd532-c3b3-4002-944c-92eed66d7dca" />




---
## Result

The **GPIO interrupt combined with a timer-based non-blocking debounce** was successfully implemented. The switch bounce was effectively filtered, preventing **false triggering**, while the **main loop continued to execute without blocking** during the debounce period. Thus, reliable switch operation and non-blocking program execution were successfully verified.



















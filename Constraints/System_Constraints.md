# Task 1: System Constraints

**System:** Automated Railway Level-Crossing Control System (ARLCCS)  
**Authors:** Muhammad Danish Anwar & Alishba Arshad

---

## 10 Identified Constraints

### C1: Barrier Closed During Train Presence
* **Rule:** The road barrier must never be open while a train is inside the crossing area.
* **Reason:** If the barrier opens while the train is passing, cars and people can enter the tracks and get hit.

### C2: Warning Signals Before Barrier Closes
* **Rule:** Warning lights and alarm bells must activate at least a few seconds before barriers start moving down.
* **Reason:** Road drivers need advance warning to stop safely so the barrier does not drop on top of a moving car.

### C3: Train Clearance for Track Entry
* **Rule:** The railway signal must not show GREEN to an approaching train unless all barriers are fully closed and locked.
* **Reason:** If the train enters while the road gate is still open, it cannot stop in time and will cause a disaster.

### C4: Complete Train Exit Before Opening
* **Rule:** The barriers must stay closed until the last carriage of the train has completely cleared the exit sensor.
* **Reason:** Opening gates while rear wagons are still passing will cause road vehicles to crash into the train.

### C5: Warning Signals Active While Barrier is Down
* **Rule:** Warning lights and audible sirens must stay ON the entire time the barrier is moving or closed.
* **Reason:** Drivers need continuous visual and sound alerts so no one tries to bypass the closed gates.

### C6: Fail-Safe on Sensor Failure
* **Rule:** If any train detection sensor fails or stops sending data, the system must immediately close barriers and turn road signals RED.
* **Reason:** It is much safer to stop road traffic by mistake than to leave gates open when a train might be coming.

### C7: Emergency Stop on Barrier Failure
* **Rule:** If a barrier gets stuck or fails to close completely, the system must turn train signals to RED and alert the control center.
* **Reason:** The train driver must be alerted as early as possible to apply emergency brakes before reaching the open crossing.

### C8: Road Traffic Signals Red During Approach
* **Rule:** Road traffic signals must show RED whenever a train is detected approaching or crossing.
* **Reason:** Road traffic must be stopped before the barriers even start moving downwards.

### C9: Dual-Track Safety Check
* **Rule:** The barriers must not open after one train leaves if a second train is detected approaching from the other track.
* **Reason:** Opening the gates between two passing trains can trap vehicles on the tracks in front of the second train.

### C10: Communication Loss Fail-Safe
* **Rule:** If the local safety unit loses communication with the main control center, the crossing must go to fail-safe closed state.
* **Reason:** The system should not operate in an unverified state without central monitoring.

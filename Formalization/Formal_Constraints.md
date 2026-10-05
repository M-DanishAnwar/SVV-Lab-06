# Boolean Variables Used

* `Train_Present`: TRUE if train is currently in crossing zone.
* `Train_Approaching`: TRUE if incoming train sensor is triggered.
* `Barrier_Open`: TRUE if road barrier is open (not down).
* `Barrier_Closed`: TRUE if road barrier is fully down and locked.
* `Warning_Active`: TRUE if warning lights and siren are ON.
* `Train_Signal_Green`: TRUE if railway signal gives train permission to enter.
* `Road_Signal_Red`: TRUE if road traffic light is showing RED.
* `Sensor_Fault`: TRUE if any detection sensor fails or goes offline.
* `Barrier_Stuck`: TRUE if barrier failed to reach closed position within time limit.
* `Train_Cleared`: TRUE if exit sensor confirms full train departure.

---

## Formalized Constraints (Logical Notation)

### 1. Formal C1 (Barrier and Train Presence)
$$Train\_Present \rightarrow \neg Barrier\_Open$$
*(If a train is present, then the barrier must NOT be open.)*

### 2. Formal C2 (Warning on Approach)
$$Train\_Approaching \rightarrow Warning\_Active$$
*(If a train is approaching, warning lights and sirens must be active.)*

### 3. Formal C3 (Train Signal Safety)
$$Train\_Signal\_Green \rightarrow Barrier\_Closed$$
*(Train can only get a green signal if barriers are fully closed.)*

### 4. Formal C4 (Train Clearance)
$$\neg Train\_Cleared \rightarrow \neg Barrier\_Open$$
*(If the train has not cleared the exit sensor, the barrier cannot open.)*

### 5. Formal C5 (Continuous Warning)
$$Barrier\_Closed \rightarrow Warning\_Active$$
*(While barrier is closed, warning signals must stay active.)*

### 6. Formal C6 (Sensor Failure Fail-Safe)
$$Sensor\_Fault \rightarrow Barrier\_Closed$$
*(If a sensor failure happens, barriers must be forced closed.)*

### 7. Formal C7 (Barrier Jam Emergency)
$$Train\_Approaching \land Barrier\_Stuck \rightarrow \neg Train\_Signal\_Green$$
*(If train is coming and barrier gets stuck, train signal must NOT be green.)*

### 8. Formal C8 (Road Traffic Stop)
$$(Train\_Approaching \lor Train\_Present) \rightarrow Road\_Signal\_Red$$
*(If train is approaching OR inside crossing, road signal must be RED.)*

### 8. Formal C8 (Road Traffic Stop)
$$(Train\_Approaching \lor Train\_Present) \rightarrow Road\_Signal\_Red$$
*(If train is approaching OR inside crossing, road signal must be RED.)*

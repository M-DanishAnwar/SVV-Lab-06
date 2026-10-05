# Task 3: Identify Constraint Violations

## Violation 1 (Breaks C1)
* **Constraint:** `Train_Present -> ¬Barrier_Open`
* **System State:**
  * `Train_Present = TRUE`
  * `Barrier_Open = TRUE`
* **What went wrong?** A train is currently passing over the road tracks, but the barriers are open.
* **How we know:** The track presence sensor reports a train on the crossing, but the barrier angle sensor still reads open/raised. This allows cars to drive straight into the moving train.

---

## Violation 2 (Breaks C2)
* **Constraint:** `Train_Approaching -> Warning_Active`
* **System State:**
  * `Train_Approaching = TRUE`
  * `Warning_Active = FALSE`
* **What went wrong?** The approach sensor detected an incoming train, but warning lights and sirens did not turn on.
* **How we know:** The approach track relay is active, but electrical current sensor on the warning lights reads zero. Drivers have no clue a train is coming.

---

## Violation 3 (Breaks C3)
* **Constraint:** `Train_Signal_Green -> Barrier_Closed`
* **System State:**
  * `Train_Signal_Green = TRUE`
  * `Barrier_Closed = FALSE`
* **What went wrong?** The train driver was given a green light to proceed, even though the road gates are still up or moving.
* **How we know:** Track signal circuit shows GREEN relay closed, while barrier limit switch shows gate is not down. The train will enter an unprotected crossing at high speed.

---

## Violation 4 (Breaks C4)
* **Constraint:** `¬Train_Cleared -> ¬Barrier_Open`
* **System State:**
  * `Train_Cleared = FALSE`
  * `Barrier_Open = TRUE`
* **What went wrong?** The front of the train crossed, but the rear wagons are still on the crossing and the barriers already opened up.
* **How we know:** Exit sensor has not triggered its cleared pulse, but gate motor controller received an OPEN command and lifted the gates. Cars will crash into the tail of the train.

# 📝 Deviation Report: DR-2026-001

## 1. Executive Summary
On February 16, 2026, during the automated vial-filling process, a critical weight excursion was detected. A single measurement recorded 500.00 mg, representing a 900% deviation from the nominal target of 50.00 mg. This event triggered a system-level critical alarm and requires a formal investigation to ensure batch integrity.

## 2. Event Description
Timestamp: 2026-02-16 06:24:15
Process Step: Fill_Vial
Equipment ID: Scale-VF-04
Observed Value: 500.00 mg
Upper Control Limit (UCL): 50.50 mg
Deviation Severity: Critical

## 3. Initial Investigation & Data Analysis
Analysis of the Manufacturing Dashboard reveals the following:

Outlier Identification: The 500mg peak is an isolated event (spike), suggesting a sensor glitch or a physical obstruction rather than a gradual process drift.

Operator Correlation: The event occurred during the shift of Operator OP_ES_03. Historical data in the "Operator Performance" chart shows this operator has a higher-than-average correlation with system alarms (17 total alarms).

Process Stability: Prior to and immediately after the excursion, the process remained stable within the 49.5mg - 50.5mg range (SPC Monitor).

## 4. Root Cause Analysis (RCA) - Preliminary
Primary Hypothesis: Electronic interference or mechanical "double-weighing" at the Fill_Vial station.
Contributing Factor: Potential lack of station-specific calibration by the operator at the start of the shift.

## 5. Proposed CAPA (Corrective and Preventive Actions)
Immediate Corrective Action:

Quarantining of the affected sub-lot for 100% manual weight verification.

Immediate re-calibration of Scale-VF-04.

Preventive Actions:

MES Logic Update: Implement a "Hard Stop" interlock in the MES if any value exceeds 100mg, preventing the vial from moving to the Capping stage.

Training: Targeted re-certification for Operator OP_ES_03 on "High-Precision Dosing Procedures."

## 6. Quality Assurance (QA) Conclusion
The detection of this excursion confirms the effectiveness of the current monitoring dashboard. However, the batch cannot be released until the mechanical integrity of the filling needle and the scale's communication bus are fully validated.

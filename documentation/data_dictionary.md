# 📖 Data Dictionary: MES Production Log
This document defines the metadata and data structures used in the MES_project, following ALCOA+ principles.

## 🗂️ Dataset Overview
Source: Synthetic Manufacturing Execution System (MES) Log.

Format: CSV (Comma Separated Values).

Scope: Monitoring of a pharmaceutical fill-finish line (Vial Weighing).

## 📋 Field Definitions
### 1. Timestamp

Data Type: DateTime

Description: The exact date and time the event was recorded by the MES.

Business Rule: Must follow ISO 8601 format. Used for time-series analysis.

### 2. Value_Measured

Data Type: Decimal

Description: The weight of the vial measured by the in-line scale in milligrams (mg).

Business Rule: Target: 50.0mg. Tolerance: ±0.5mg. Values outside this range trigger a deviation.

### 3. Operator

Data Type: String

Description: The unique identifier of the technician authenticated in the MES station.

Business Rule: Used for accountability (Attributable).

### 4. Step (Process Phases)

Data Type: String

Description: The specific stage of the manufacturing cycle. Defined as follows:

Check_Tare: The initial weighing of the empty glass vial. This ensures the container's weight is zeroed out before adding the drug product.

Fill_Vial: The core dosing stage where the liquid or powder medicine is injected into the vial. Critical point for the 500mg deviation found in this project.

Capping: The mechanical placement and sealing of the rubber stopper and aluminum cap to ensure container closure integrity (CCI).

Labeling: The application of the printed label containing the batch number, expiry date, and product info. Crucial for patient safety and serialization.

Weight_Final: The end-of-line verification weight. It confirms the total mass of the finished product before it enters secondary packaging.

### 5. Critical_Alarm

Data Type: Boolean (0/1)

Description: Binary flag indicating if a system interlock or critical alarm was triggered.

Business Rule: 0: Normal operation. 1: Critical failure/alarm detected.

## 🔍 Data Quality Notes
Unit of Measure: All weights are recorded in milligrams (mg).

Outlier Handling: The value of 500.00 mg in the Fill_Vial step is identified as a "Critical Peak Excursion," triggering a formal investigation.

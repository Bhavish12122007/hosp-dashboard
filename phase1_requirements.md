# Phase 1: Dynamic Hospital Performance Dashboard Requirements

## 1. Data Sources
| System / Department | Data Available | Format / Access | Update Frequency | Notes |
|--------------------|----------------|----------------|----------------|-------|
| Bed Management | Occupied beds, total beds, ward info | API / DB / CSV | Real-time / daily |  |
| OPD Scheduling | Appointment times, patient check-in | API / DB / CSV | Real-time |  |
| Billing | Amount billed, collected | API / DB | Daily / weekly |  |
| Lab System | Test requested, completed, SLA | API / DB | Real-time |  |
| Pharmacy | Stock, prescriptions dispensed | API / DB | Daily |  |
| Patient Surveys | NPS score, feedback, complaints | CSV / API | Weekly |  |

## 2. KPIs
| KPI | Formula / Calculation | Frequency | Alert Threshold | Notes |
|-----|---------------------|-----------|----------------|-------|
| Bed Occupancy Rate | (Occupied Beds / Total Beds) * 100 | Real-time | >15% deviation |  |
| Average OPD Wait Time | Avg(check-in → consultation) | Real-time | >15% deviation |  |
| Billing Collection Rate | (Amount Collected / Amount Billed) * 100 | Daily | <85% collection |  |
| Lab TAT Compliance | (Tests Completed within SLA / Total Tests) * 100 | Real-time | <90% |  |
| 30-day Readmission Rate | (Readmitted Patients / Total Discharged) * 100 | Weekly | >15% deviation |  |
| NPS | (% Promoters - % Detractors) | Weekly | <50 |  |

## 3. Alerts & Recommendations
| KPI | Type of Alert | Priority | Example Corrective Action | Notes |
|-----|---------------|---------|-------------------------|-------|
| Bed Occupancy Rate | High occupancy alert | High | Move patients to overflow ward / reassign beds |  |
| Average OPD Wait Time | Spike alert | High | Reassign doctors / activate extra slots |  |
| Billing Collection Rate | Low collection | Medium | Send reminders / audit billing process |  |
| Lab TAT Compliance | SLA miss | High | Reassign lab technicians / prioritize urgent tests |  |
| 30-day Readmission Rate | Spike in readmissions | Medium | Review discharge protocols / follow-up calls |  |
| NPS | Low satisfaction | Low | Investigate patient complaints / improve service |  |

## 4. Role-Based Dashboard Views
| Role | Access Level | Data / KPIs Shown | Actions Allowed |
|------|-------------|-----------------|----------------|
| CEO | Full hospital-wide | All KPIs, trends, summary | View only |
| Department Head | Department-level | KPIs for their department | View + recommend actions |
| Floor Supervisor | Operational level | Real-time alerts, actionable recommendations | Execute actions / acknowledge alerts |

## 5. Update Frequency & Data Flow
| Data Source | Frequency | Method of Update | Notes |
|------------|-----------|----------------|-------|
| Bed Management | Real-time | API / Event-driven | Push updates via webhook if possible |
| OPD Scheduling | Real-time | API / Polling |  |
| Billing | Daily | API / DB |  |
| Lab System | Real-time | API / Event |  |
| Pharmacy | Daily | API / DB |  |
| Surveys | Weekly | CSV / API |  |

# Clinic Appointment & Diagnostics Platform — ER Diagram

An entity-relationship diagram for a clinic management system covering appointments, consultations, diagnostic tests, reports, and payments.

## Entities

| Entity | Description |
|---|---|
| `Specialty` | Doctor specializations (e.g. Cardiology, Dermatology) |
| `Doctor` | Clinic doctors, each linked to a specialty |
| `Patient` | Registered patients |
| `Appointment` | A booking made by a patient with a doctor |
| `Consultation` | The actual visit that results from an appointment |
| `DiagnosticTest` | Master list of available lab/diagnostic tests |
| `PrescribedTest` | A test prescribed during a specific consultation |
| `Report` | Lab result generated for a prescribed test |
| `Payment` | Payment record tied to an appointment |

## Key Design Decisions

- **Appointment and Consultation are separate** — not every appointment results in a visit (cancellations, no-shows)
- **PrescribedTest is a junction entity** — one consultation can prescribe many tests
- **Report links to PrescribedTest** — traceable back to the exact consultation and patient
- **Specialty is its own entity** — not just an attribute on Doctor, allows future extension
- **Payment is tied to Appointment** — billing happens at booking/check-in level

## Files

- `clinic_erd.eraser` — source diagram file (Eraser.io)
- `clinic_erd.png` — exported image of the diagram

## Tools Used

- [Eraser.io](https://eraser.io) for diagramming

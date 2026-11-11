# 🏢 Elevator Control System — FSM Control

Real Elevator Simulation using **Finite State Machine (FSM)**.
Digital Logic Design Project — HTML, CSS, JavaScript.

🔗 **Live Demo:** https://github.com/HK-Cyber-enthusiast/FSM-ELEVATOR-CONTROL-SYSTEM

## ✨ Features
- Live 4-Floor Elevator Animation
- Door Open / Close Simulation
- Inside Lift Panel + Outside Call Buttons
- Real FSM Logic — Not `cur+1`
- Emergency (E=1) — Immediate Logical Reset to G
- K-Maps with Groupings
- State Table + State Diagram
- Busy Lock — No Double Movement

## 🧠 State Encoding
| Floor | QA QB |
|-------|-------|
| G     | 00    |
| F1    | 01    |
| F2    | 10    |
| F3    | 11    |

## 🔢 Boolean Equations
QA+ = QB.X + QA.X + QA.QB.X'
QB+ = QB'.X + QA.QB' + QA.QB.X
Z1 = X'.(QA+QB)
Z0 = X.(QA'+QB')
D_fsm = QA'.QB'.X' + QA.QB.X + E

## 🚪 Door Logic
NORMAL:    D_actual = D_fsm OR ARR
EMERGENCY: D_physical = D_fsm AND (phys == G)

- `X = 1` → UP
- `X = 0` → DOWN
- `E = 1` → Logical State = 00 (G) Immediately
- `ARR = 1` → Lift Reached Target

## 🗺️ K-Maps
- Row = X, Column = QA QB (00 01 11 10)
- QA+ : Minterms 3, 5, 6, 7
- QB+ : Minterms 1, 4, 5, 7
- Z1  : Minterms 2, 4, 6
- Z0  : Minterms 1, 3, 5

## 📊 State Table
| QA | QB | X | QA+ | QB+ | Z1 | Z0 | D_fsm |
|----|----|---|-----|-----|----|----|-------|
| 0  | 0  | 0 | 0   | 0   | 0  | 0  | 1     |
| 0  | 0  | 1 | 0   | 1   | 0  | 1  | 0     |
| 0  | 1  | 0 | 0   | 0   | 1  | 0  | 0     |
| 0  | 1  | 1 | 1   | 0   | 0  | 1  | 0     |
| 1  | 0  | 0 | 0   | 1   | 1  | 0  | 0     |
| 1  | 0  | 1 | 1   | 1   | 0  | 1  | 0     |
| 1  | 1  | 0 | 1   | 0   | 1  | 0  | 0     |
| 1  | 1  | 1 | 1   | 1   | 0  | 0  | 1     |

## 🔄 State Diagram
G ⇄ F1 ⇄ F2 ⇄ F3
G  X=0 → G (Stay)
F3 X=1 → F3 (Stay)
E=1 → G (From ANY State)

## 🚀 How To Run
1. Download `index.html`
2. Double-click to open in browser
3. No installation needed

## 🛠️ Tech Used
HTML, CSS, JavaScript, FSM, Boolean Algebra, K-Map

# QA Project – Boundary Value Analysis & Decision Table Testing

## Overview
This project demonstrates the application of Boundary Value Analysis (BVA), Equivalence Partitioning, and Decision Table Testing techniques.

The goal is to design effective test cases for input validation and business logic scenarios.

---

## Scope
- Boundary Value Analysis (BVA)
- Equivalence Partitioning
- Decision Table Testing
- Test case design for edge cases and validation logic

---

## Equivalence Partitioning & Boundary Value Analysis – Speed Camera System

### Business Requirement
A system processes vehicle speed and issues fines based on speed limits:

- 0 – 49.99 km/h → No fine  
- 50 – 59.99 km/h → $50 fine  
- 60 – 64.99 km/h → $100 fine  
- 65 – 99.99 km/h → $400 fine  
- 100+ km/h → $1500 fine + 3-month license suspension  

---

## Equivalence Partitions

| Class | Range | Description | Example Value |
|------|------|-------------|---------------|
| K0 | < 0 | Invalid input | -1 |
| K1 | 0 – 49.99 | No fine | 45.20 |
| K2 | 50 – 59.99 | $50 fine | 54.65 |
| K3 | 60 – 64.99 | $100 fine | 63.20 |
| K4 | 65 – 99.99 | $400 fine | 75.21 |
| K5 | 100+ | $1500 + suspension | 120 |

---

## Boundary Value Analysis (BVA)

**2BVA**

(-0.01; 0; 49.99; 50; 59.99; 60; 64.99; 65; 99.99; 100)

**2BVA + examples of speeds**

(-1; -0.01; 0; 45.20; 49.99; 50; 54.65; 59.99; 60; 63.20; 64.99; 65; 75.21; 99.99; 100; 120)

**3BVA**

(-0.01; 0; 0.01; 49.98; 49.99; 50; 50.01; 59.98; 59.99; 60; 60.01; 64.98; 64.99; 65; 65.01; 99.98; 99.99; 100; 100.01)

**3BVA + examples of speeds**

(-1; -0.01; 0; 0.01; 45.20;  49.98; 49.99; 50; 50.01; 54.65; 59.98; 59.99; 60; 60.01; 63.20; 64.98; 64.99; 65; 65.01; 75.21; 99.98; 99.99; 100; 100.01; 120)

---
## Equivalence Partitioning & Boundary Value Analysis – Student Behavior System

## Business Requirement

| Partition | Range | Example | Result |
|----------|------|--------|--------|
| P1 | < 30 | 25 | Inappropriate |
| P2 | 30–60 | 47 | Adequate |
| P3 | 61–89 | 80 | Sufficient |
| P4 | 100–119 | 110 | Good behavior |
| P5 | ≥120 | 150 | Very good behavior |
| Invalid | 90–99 | 95 | Invalid |

## Boundary Value Analysis (BVA)

**2BVA**

(29; 30; 59; 60; 89; 90; 99; 100; 119; 120)

**2BVA + examples**

(-1; 25; 29; 30; 47; 59; 60; 80; 89; 90; 95; 99; 100; 110; 119; 120; 150)

**3BVA**

(29; 30; 31; 59; 60; 61; 89; 90; 91; 99; 100; 101; 119; 120; 121)

**3BVA + examples**

(-1; 25; 29; 30; 31; 47; 59; 60; 61; 80; 89; 90; 95; 99; 100; 101; 110; 119; 120; 121; 150)

---

## Decision Table

### Business Rule (Requirement)
A system provides benefits to store employees based on:
- Length of service
- Employee evaluation

### Rules:
- If employee has worked more than 1 year → eligible for medical benefits
- If rating > 4 → receives vacation voucher
- If BOTH conditions are met → receives bonus

### Conditions:
- Worked > 1 year
- Rating > 4

### Actions:
- Medical benefits
- Vacation voucher
- Bonus

| **Condition**         | TC1 | TC2 | TC3 | TC4 |
|-------------------|-----|-----|-----|-----|
| Worked > 1 year   | T   | T   | F   | F   |
| Rating > 4        | T   | F   | T   | F   |
|-------------------|-----|-----|-----|-----|
| **Actions**|      
| Medical benefits  | T   | T   | F   | F   |
| Vacation voucher  | T   | F   | T   | F   |
| Bonus             | T   | F   | F   | F   |

---

## Skills Demonstrated
- Test design techniques  
- Boundary analysis  
- Logical condition testing  
- Analytical thinking in QA  

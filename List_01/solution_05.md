# 📘 Task 5 — Buffon's Needle Experiment

## 🔹 Useful Definitions and Formulas

### 1. Sample Space
The sample space is the set of all possible elementary outcomes of a random experiment:

$$
\Omega = \{\omega\}
$$

---

### 2. Elementary Outcome
An elementary outcome is a **single complete result** of the experiment.

---

### 3. Continuous Sample Space
A sample space is **continuous** if outcomes are described by real numbers (intervals), not discrete values.

---

## ✅ Problem Solution

### 🔹 Given:

- A needle of length \( L \) is thrown randomly  
- The plane contains parallel lines spaced at distance \( d \)  
- The position and orientation of the needle determine the outcome  

---

## 1️⃣ Parameters Describing an Outcome

A single outcome is determined by two variables:

### ✔ Distance from the nearest line:

$$
x \in [0, d/2]
$$

- \(x\) is the distance from the **center of the needle** to the nearest line  
- By symmetry, we only consider half the distance between lines  

---

### ✔ Angle of orientation:

$$
\theta \in [0, \pi/2]
$$

- \(\theta\) is the angle between the needle and the parallel lines  
- Due to symmetry, angles beyond \(\pi/2\) repeat behavior  

---

## 2️⃣ Representation of an Elementary Outcome

Each elementary outcome can be written as:

$$
(x, \theta)
$$

where:

$$
x \in [0, d/2], \quad \theta \in [0, \pi/2]
$$

This pair fully describes:
- the position of the needle  
- the orientation of the needle  

---

## 3️⃣ Sample Space \( \Omega \)

The sample space is the set of all possible pairs \((x, \theta)\):

$$
\Omega = \{(x, \theta) : x \in [0, d/2], \; \theta \in [0, \pi/2]\}
$$

---

## 4️⃣ Interpretation

Each elementary outcome represents:

- a **specific position** of the needle (distance from the nearest line), and  
- a **specific orientation** (angle with respect to the lines)

---

## 5️⃣ Why the Sample Space is Continuous

Unlike previous tasks (coin tosses, dice, cards), here:

- \(x\) can take **any real value** in an interval  
- \(\theta\) can take **any real value** in an interval  

Thus:

$$
\Omega \subset \mathbb{R}^2
$$

There are infinitely many possible outcomes, not a finite or countable set.

---

### 📌 Conclusion:

- Previous experiments → **discrete sample spaces** (finite/countable outcomes)  
- Buffon's needle → **continuous sample space** (uncountably infinite outcomes)

---

## 🔹 Key Insight

Each outcome is described by continuous variables:

$$
(x, \theta) \in [0, d/2] \times [0, \pi/2]
$$

This makes Buffon's needle experiment fundamentally different from discrete probability models.

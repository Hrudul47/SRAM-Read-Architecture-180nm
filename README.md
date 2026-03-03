🔷 6T SRAM Cell with Dynamic Sense Amplifier – LTspice Simulation (180nm CMOS)
📌 Project Overview

This project presents the design and simulation of a 6-Transistor (6T) CMOS SRAM cell integrated with a dynamic latch-type sense amplifier using 180nm CMOS technology in LTspice.

The complete system includes:

6T SRAM storage cell

Bitline precharge circuit

Equalization transistor

Latch-based dynamic sense amplifier

Wordline (WL) control

Sense enable (SAEN) control

Supply voltage: 1.8 V

Technology node: 180 nm

🧩 Circuit Architecture
1️⃣ 6T SRAM Cell

Two cross-coupled CMOS inverters

Two access NMOS transistors

Differential bitlines (BL, BLB)

2️⃣ Precharge Circuit

Two PMOS precharge devices

One equalization PMOS

Controlled by Pre_Charge signal

3️⃣ Dynamic Sense Amplifier

Cross-coupled PMOS pair

Cross-coupled NMOS pair

Tail NMOS transistor (SAEN controlled)

Input gating transistors

⚙️ Technology Parameters
Parameter	Value
Technology Node	180 nm
VDD	1.8 V
Channel Length (L)	0.18 µm
Bitline Capacitance	100–150 fF
Simulation Tool	LTspice 26
MOS Model	Level-1 (Shichman–Hodges)
📐 Transistor Sizing
SRAM Cell
Device	Width (µm)	Length (µm)
Pull-Up PMOS	0.6 – 2 µm	0.18
Pull-Down NMOS	1 µm	0.18
Access NMOS	0.7 – 1.2 µm	0.18
Sense Amplifier
Device	Width (µm)	Length (µm)
Regeneration PMOS	2 µm	0.18
Regeneration NMOS	3 µm	0.18
Tail NMOS	3 µm	0.18
Precharge PMOS	2–3 µm	0.18
🔢 Ratio Calculations
1️⃣ Cell Ratio (CR)
𝐶
𝑅
=
𝑊
𝑝
𝑢
𝑙
𝑙
−
𝑑
𝑜
𝑤
𝑛
𝑊
𝑎
𝑐
𝑐
𝑒
𝑠
𝑠
CR=
W
access
	​

W
pull−down
	​

	​


Example:

𝐶
𝑅
=
1
1.2
=
0.83
CR=
1.2
1
	​

=0.83

A CR < 1 indicates moderate read stability.

2️⃣ Pull-Up Ratio (PR)
𝑃
𝑅
=
𝑊
𝑎
𝑐
𝑐
𝑒
𝑠
𝑠
𝑊
𝑝
𝑢
𝑙
𝑙
−
𝑢
𝑝
PR=
W
pull−up
	​

W
access
	​

	​


Example:

𝑃
𝑅
=
1.2
2
=
0.6
PR=
2
1.2
	​

=0.6

This ensures write-ability of the cell.

⏱ Operating Phases
🔹 1. Precharge Phase

Pre_Charge = 0

BL and BLB precharged to VDD

Equalization transistor ON

SAEN = 0 (sense amp disabled)

🔹 2. Read Development

WL = 1

One bitline slightly discharges

Small differential voltage develops (≈ 50–150 mV)

🔹 3. Sense Amplification

SAEN = 1

Tail transistor turns ON

Cross-coupled latch regenerates

Full rail-to-rail output generated

📊 Observed Simulation Behavior

From transient simulation:

Proper precharge to 1.8 V

Differential bitline development

Strong regenerative amplification

Rail-to-rail sensing within few nanoseconds

Slight negative kickback due to dynamic behavior (normal)

🔬 Stability Analysis
Hold SNM

Extracted using DC butterfly curve.

𝑆
𝑁
𝑀
ℎ
𝑜
𝑙
𝑑
≈
220
–
250
 mV
SNM
hold
	​

≈220–250 mV
Read SNM
𝑆
𝑁
𝑀
𝑟
𝑒
𝑎
𝑑
≈
160
–
190
 mV
SNM
read
	​

≈160–190 mV

Read SNM < Hold SNM (expected behavior).

⚡ Leakage & Power

Measured standby leakage (hold mode):

𝐼
𝑙
𝑒
𝑎
𝑘
𝑎
𝑔
𝑒
≈
20
–
40
 nA
I
leakage
	​

≈20–40 nA

Standby power:

𝑃
𝑠
𝑡
𝑎
𝑛
𝑑
𝑏
𝑦
=
𝑉
𝐷
𝐷
×
𝐼
𝑙
𝑒
𝑎
𝑘
𝑎
𝑔
𝑒
P
standby
	​

=V
DD
	​

×I
leakage
	​

𝑃
𝑠
𝑡
𝑎
𝑛
𝑑
𝑏
𝑦
≈
36
–
72
 nW
P
standby
	​

≈36–72 nW
🔍 Key Observations

Dynamic latch shows strong positive feedback behavior

Proper differential sensing achieved

Slight kickback noise observed during regeneration

Convergence warnings due to Level-1 MOS model (expected)

Simulation stable under 100–150 fF bitline loading

🛠 Simulations Performed

Transient read operation

Precharge timing verification

Sense enable timing sweep

Bitline capacitance loading analysis

Leakage current measurement

DC sweep for butterfly curve extraction

📈 Performance Summary
Parameter	Value
VDD	1.8 V
Bitline Capacitance	100–150 fF
Hold SNM	≈ 230 mV
Read SNM	≈ 180 mV
Standby Leakage	20–40 nA
Standby Power	≈ 60 nW
Regeneration Delay	Few ns
🧠 Technical Insights

Proper transistor sizing is critical for stability.

Removing unintended ground connections is essential in dynamic circuits.

Latch-type sense amplifiers exhibit kickback due to capacitive coupling.

Level-1 MOS models produce short-channel warnings but are acceptable for conceptual validation.

📌 Conclusion

The 6T SRAM cell integrated with a dynamic latch-type sense amplifier has been successfully designed and validated in 180nm CMOS using LTspice.

The design demonstrates:

✔ Correct read operation
✔ Stable hold behavior
✔ Proper dynamic regeneration
✔ Realistic bitline loading behavior
✔ Acceptable noise margins

This project provides a strong foundation for understanding SRAM read architecture and sense amplifier design.

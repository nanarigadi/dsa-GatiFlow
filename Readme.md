The 4 Systems
	1.	Static → The old-school fixed timer. Like 30 seconds green, then red, repeat. Doesn’t care how many cars are waiting.
	2.	Dynamic (Proportional) → Looks at the queues and tries to split green time proportionally based on demand.
	3.	Subtractive → If some road has very low demand, we cut its green time short and give that time to the busier roads.
	4.	Tuned (GatiFlow) → I added:
	•	Weighted queues (some directions matter more).
	•	Minimum/maximum green limits so no road starves.
	•	Bonus seconds if one lane is way more crowded than the rest.
	•	Flexibility: if one side doesn’t use up its green fully, the leftover goes to the other lane.

How it Works
	•	Time runs for 1800 seconds (30 minutes).
	•	Each lane gets cars every minute, either fixed or using a Poisson random process (to make it realistic, since cars don’t arrive like robots).
	•	A car takes P = 2 seconds to clear the intersection.
	•	We keep track of:
	•	How many vehicles cleared (throughput).
	•	How long vehicles waited on average (waiting time).

What it Measures:

I ran two types of experiments:
	1.	Single deterministic run → same traffic every time.
	2.	Monte Carlo runs → 30 runs with random arrivals (Poisson). This gives the “average real-life” picture.




How to run :
javac TrafficSimTuned.java
java TrafficSimTuned

okie byie

# Analysis of Investment Manager Simulations: "The Myth of Talented Investors"

This code models a key idea: the success of many investment managers may be the result of randomness rather than true skill.

> “The success of most fund managers is randomness, not skill.”

## What does the simulation do?

1. 5,000 managers start with a zero balance.  
2. Each year, their profit or loss is determined by a coin flip (50/50).  
3. Only those who made a profit survive. The rest are "out of the game."  
4. After 5 years, only a handful of "successful" managers remain.  

## What is this about?

- **Cognitive bias**: We tend to believe that survivors are "investment geniuses," even though their success is purely due to luck.  
- **Survivorship bias**: When observing top managers, we don't see the thousands of losers who disappeared along the way.  
- **Industry critique**: Hedge funds and asset managers often charge massive fees for “skills” that are indistinguishable from randomness.  

## How to interpret the results?

```
Year 1: Survived 2487/5000  # 50% survived  
Year 2: Survived 1231/5000  # 25%  
...  
Year 5: Survived 155/5000  # ~3% — the "stars"  
```

These 155 managers didn’t prove their superiority—they are simply a statistical "coin toss."

## Where does this occur in reality?

- **Stock market**: 90% of traders fail to outperform the S&P 500 in the long run.  
- **Startups**: The success of many unicorn companies is due to market noise, not founder genius.  
- **Science**: Many "breakthrough studies" fail to replicate in repeated experiments (see "replication crisis").  

## Philosophical context

This code illustrates ideas from:

- **Nassim Taleb (*Fooled by Randomness*)** — Success is often mistakenly attributed to skill.  
- **Epictetus** — “Men are disturbed not by things, but by the view they take of them.” We believe in narratives even when they are false.  

## Simulation Code

```python
import random

class Simulation:
    def __init__(self, years=5, population=5000):
        self.years = years
        self.population = population

    def simulate_year(self):
        """Returns True (profit) with a probability of 50%."""
        return random.random() > 0.5

    def run_simulation(self):
        managers = self.population
        for year in range(1, self.years + 1):
            profits = [self.simulate_year() for _ in range(managers)]
            managers = sum(profits)  # Count of True (profitable)
            print(f"Year {year}: Survived {managers}/{self.population}")

sim = Simulation(years=5, population=5000)
sim.run_simulation()
```
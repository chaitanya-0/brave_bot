# Brave Bot Project

Welcome to my **Brave Bot** project repository! This work was done as part of the 520 course at Rutgers University (Spring 2024). The focus of these projects is to build bots that can navigate a spaceship infested by aliens, locate and rescue hidden crew members, and make informed decisions under uncertain conditions.

## Part 1: Known Locations
In the first project, I represented the spaceship as a randomly generated grid environment. The bot's primary mission was to rescue the Captain while avoiding randomly moving aliens.

### Implemented Bots:
- **Bot 1:** Calculates a fixed shortest path to the Captain at the start and strictly follows this path, ignoring alien movements.
- **Bot 2:** Recalculates the shortest path every timestep, adapting dynamically to the aliens' current positions.
- **Bot 3:** Improves on Bot 2 by also steering clear of cells adjacent to aliens, creating safer paths whenever possible.
- **Bot 4:** My custom design builds upon Bot 3, proactively exploring alternative routes around potential dangers, especially useful when direct paths are blocked.

### Analysis and Observations:
I ran extensive simulations with varying numbers of aliens (K) to evaluate each bot's performance. Key metrics included the success rate of rescuing the Captain within 1000 timesteps and the survival rate if rescue attempts failed. To efficiently find paths, I implemented the **A\*** algorithm with a Manhattan distance heuristic. The results highlighted the clear advantage of regularly recalculating paths and strategically avoiding danger.

## Part 2: Unknown Locations
The second project introduced uncertainty, requiring bots to use noisy sensor data to make decisions. Bots navigated based on probabilistic estimates of alien and crew member locations.

### Implemented Bots:
- **Bot 1:** Uses Bayesian updating to keep track of the probability of aliens and crew locations, adjusting its beliefs with new sensor information at each step.
- **Bot 2:** Enhances Bot 1 with additional heuristics designed to manage uncertainty more effectively, balancing sensor reliability and proactive decision-making to find crew members efficiently.

### Analysis and Observations:
Testing different sensor parameters (`k` and `α`) revealed insights into the effectiveness of sensor sensitivity versus information quality. Metrics evaluated included average moves needed, success probability, and the average number of crew members rescued. Bot 2 consistently outperformed Bot 1, showing the advantage of intelligently managing uncertainty and leveraging sensor data for safer, faster rescues.

## Repository Contents:
- `known_locations.ipynb`: Implementation and detailed analyses of Bots 1 through 4 for Project 1.
- `unknown_locations.ipynb`: Implementation and analysis for Bots 1 and 2 in Project 2.

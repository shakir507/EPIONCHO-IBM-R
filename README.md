# Onchocerciasis Transmission Dynamics Simulation Model

This repository contains a simulation model for the transmission dynamics of onchocerciasis (river blindness) in a human population. The model incorporates the life cycle of the parasite *Onchocerca volvulus* and its vector, the blackfly. It is individual-based for humans but population-based for the parasite stages in the blackfly.

## Model Overview

The model simulates the following key processes:

1. **Treatment Coverage**: Determines which individuals will be treated based on their compliance and age, adjusting the coverage accordingly.

2. **Parasite Dynamics in Humans**: Simulates the change in the number of microfilariae (mf) in each human, accounting for the fecundity of adult worms, mf mortality, and the effects of ivermectin treatment.

3. **Parasite Dynamics in Blackflies**: Calculates the dynamics of the parasite's life stages (L1, L2, L3 larvae) in the blackfly population, assuming equilibrium conditions.

4. **Infection Acquisition in Humans**: Calculates the rate of new infections in humans based on the mean number of L3 larvae in the fly population.

5. **Mf Prevalence and Intensity**: Estimates mf prevalence and intensity in the human population based on the number of mf in a skin snip.

## Simulation Process

The main simulation loop (`ep.equi.sim`) performs the following steps:

- Updates the age of individuals and simulates births and deaths.
- Calculates individual exposure to blackfly bites, influencing the rate of new infections.
- Updates the dynamics of adult worms and mf within humans.
- Updates the dynamics of parasite life stages in the blackfly population.
- Tracks the prevalence and intensity of mf in the human population over time.
- If treatment is being administered, updates the treatment status of individuals and adjusts the dynamics of worms and mf accordingly.

## Output

The simulation returns:

- The final state of the human population.
- The prevalence of mf.
- The mean mf intensity per skin snip.

## Usage

The model is used to study the impact of mass drug administration (MDA) with ivermectin on the transmission and control of onchocerciasis. It can simulate different scenarios based on the treatment coverage, treatment interval, and duration of the intervention.

## Authors

- [Your Name]

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

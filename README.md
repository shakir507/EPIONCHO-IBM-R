# EPIONCHO-IBM

The provided code is a simulation model for the transmission dynamics of onchocerciasis (river blindness) in a human population, incorporating the life cycle of the parasite Onchocerca volvulus and its vector, the blackfly. The model is individual-based for humans but population-based for the parasite stages in the blackfly. Here's a summary of the logical flow:

    Initialization: The model sets up various parameters related to the human population, parasite life stages, treatment effects, and simulation settings.

    Treatment Coverage: The function os.cov calculates which individuals will be treated based on their compliance and age, adjusting the coverage accordingly.

    Parasite Dynamics in Humans: The change.micro function simulates the change in the number of microfilariae (mf) in each human using the Runge-Kutta 4th order method (RK4). It accounts for the fecundity of adult worms, mf mortality, and the effects of ivermectin treatment.

    Parasite Dynamics in Blackflies: The functions calc.L1, calc.L2, and calc.L3 calculate the dynamics of the parasite's life stages (L1, L2, L3 larvae) in the blackfly population, assuming equilibrium conditions.

    Infection Acquisition in Humans: The function Wplus1.rate calculates the rate of new infections in humans based on the mean number of L3 larvae in the fly population.

    Mf Prevalence and Intensity: The function mf.per.skin.snip calculates the number of mf in a skin snip for all people, which is used to estimate mf prevalence and intensity in the human population.

    Main Simulation Loop (ep.equi.sim):
        The simulation runs for a specified number of iterations, representing the passage of time.
        At each iteration, the model updates the age of individuals, determines which individuals die, and simulates the birth of new individuals.
        The model calculates the exposure of individuals to blackfly bites, which influences the rate of new infections.
        The dynamics of adult worms and mf within humans are updated using the respective functions.
        The dynamics of parasite life stages in the blackfly population are updated.
        The model tracks the prevalence and intensity of mf in the human population over time.
        If treatment is being administered, the model updates the treatment status of individuals and adjusts the dynamics of worms and mf accordingly.

    Output: The simulation returns the final state of the human population, the prevalence of mf, and the mean mf intensity per skin snip.

The model is used to study the impact of mass drug administration (MDA) with ivermectin on the transmission and control of onchocerciasis. It can simulate different scenarios based on the treatment coverage, treatment interval, and duration of the intervention.
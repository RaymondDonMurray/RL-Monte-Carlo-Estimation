# Monte Carlo Methods in Reinforcement Learning

**Course**: CS 374R - Reinforcement Learning
**Program**: UT Austin Masters in Data Science
**Assignment**: Programming Assignment #3

## Overview

This project implements Monte Carlo methods for reinforcement learning, specifically focusing on off-policy evaluation techniques. The implementation explores how agents can learn to estimate value functions from experience without requiring a complete model of the environment.

## Learning Objectives

- Understand Monte Carlo methods for value function estimation
- Explore the difference between on-policy and off-policy learning
- Implement importance sampling techniques for off-policy evaluation
- Work with discrete state and action spaces in Gymnasium environments

## Key Concepts Covered

### Monte Carlo Methods
Monte Carlo methods learn value functions directly from episodes of experience without requiring knowledge of the environment's dynamics. These model-free methods are particularly useful when:
- The environment dynamics are unknown or complex
- Learning from complete episodes is feasible
- Sample-based learning is preferred over dynamic programming

### Off-Policy Learning
Off-policy methods allow learning about one policy (the target policy) while following a different policy (the behavior policy). This enables:
- Learning from historical data
- Safe exploration strategies
- Separation of exploration and exploitation

### Importance Sampling
Two variants of importance sampling are explored in this project:
- **Weighted Importance Sampling**: Lower variance, biased (approaches unbiased asymptotically)
- **Ordinary Importance Sampling**: Unbiased, higher variance

## Technologies Used

- **Python 3.x**: Primary programming language
- **NumPy**: Numerical computations and array operations
- **Gymnasium**: Reinforcement learning environments
- **Additional libraries**: tqdm, matplotlib, tabulate

## Test Results

### Test Execution
```bash
python test.py monte_carlo
```

### Test Summary
✅ **All tests passed** (11/11 tests, 27.133 seconds)

### Test Coverage

**Equivalence Testing**
- ✅ On-policy case: Both importance sampling variants produce equivalent results

**Ordinary Importance Sampling Tests**
- ✅ OneStateMDP with RandomPolicy → OneStateMDPOptimalPolicy
- ✅ GridWorld2x2 with RandomPolicy → GridWorld2x2OptimalPolicy
- ✅ OneStateMDP with UnequalWeightPolicy → RandomPolicy
- ✅ OneStateMDP with RandomPolicy → RandomPolicy
- ✅ GridWorld2x2 with RandomPolicy → RandomPolicy

**Weighted Importance Sampling Tests**
- ✅ OneStateMDP with RandomPolicy → OneStateMDPOptimalPolicy
- ✅ GridWorld2x2 with RandomPolicy → GridWorld2x2OptimalPolicy
- ✅ GridWorld2x2 with UnequalWeightPolicy → RandomPolicy
- ✅ OneStateMDP with RandomPolicy → RandomPolicy
- ✅ GridWorld2x2 with RandomPolicy → RandomPolicy

### Test Environments
- **OneStateMDP-v0**: Simple single-state environment
- **GridWorld2x2-v0**: 2x2 grid navigation environment

### Test Policies
- **RandomPolicy**: Uniform random action selection
- **OptimalPolicy**: Environment-specific optimal policies
- **UnequalWeightPolicy**: Non-uniform random policy

## Setup

```bash
# Install dependencies
pip install -r requirements.txt

# Run tests
python test.py monte_carlo

# Run visualizations
python run.py monte_carlo --help
```

## Project Structure

The implementation follows standard reinforcement learning patterns:
- Discrete observation and action spaces
- Episode-based learning
- Policy evaluation (prediction, not control)
- Trajectory-based updates

## References

- Sutton, R. S., & Barto, A. G. (2018). *Reinforcement Learning: An Introduction* (2nd ed.). MIT Press.
  - Chapter 5: Monte Carlo Methods

## Academic Integrity

This project was completed in accordance with the UT Austin Academic Honor Code. The implementation represents original work completed for educational purposes in the MSDS Reinforcement Learning course.

Per course policy:
- Solutions are not shared publicly
- Implementation details are kept private
- Work represents individual understanding and effort

---

**Note**: This repository contains educational materials. For implementation details and code, please refer to the official course materials or Sutton & Barto's textbook.

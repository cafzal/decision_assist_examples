## Decision Assistant

### Overview
#### What? 
A tool powered by AI models and multi-objective optimization to help with complex decisions.

#### Why? 
Decisions are hard, often due to ambiguous framing, incomplete information, and complex trade offs. 
The tool helps you frame the problem and navigate solution trade offs with guidance. In the future it'll expand upstream in your workflow to help gather data and downstream to bridge the divide from decision to action.

#### Why now? 
It's easier than ever to frame problems, source relevant data, and compute solutions with the help of large language models, optimization algorithms, rich data stores, and web services for compute.

### Key Concepts
Before diving into usage, it's helpful to understand these core concepts:

#### Problem Framing
- **Domain**: The broad category of your decision (typically along the lines of select/plan/balance XYZ)
- **Context**: Additional details that help frame the problem (constraints, circumstances, etc.)
- **Objectives**: What you're trying to achieve (drivers, budget, priorities, constraints)

#### Decision Components
- **Objectives**: Your goals, each with:
  - Direction: Should this be maximized or minimized?
  - Aggregation: How should multiple options' scores be combined? (sum/average)
  - Unit: The measurement unit (dollars, percentage, etc.)
- **Options**: The different choices you're considering
- **Scores**: How well each option performs against each objective given the objective unit (e.g. score, cost, etc.)

#### Data Requirements
- **Structured Input**: Clear objectives with directions and units
- **Consistent Scoring**: Options scored against all objectives, mindful of unit and aggregation
- **Complete Information**: All relevant factors considered in objectives

#### Optimization Approaches
- **Binary Selection**: Choose one (exclusive) or more options (all-or-nothing)
  - Example use cases: Vendor selection, tool choice, single-item purchases
- **Proportional Allocation**: Distribute resources across options subject to a given range
  - Example use cases: Portfolio management, resource allocation

#### Results Interpretation
- **[Pareto Front](https://en.wikipedia.org/wiki/Pareto_front)**: The set of optimal solutions where you can't improve one objective without making another worse
- **Trade-offs**: Understanding how improving one objective affects others
- **Solution Selection**: Choosing the option that represents the best balance of objectives for your needs

### Workflow
#### [1] Define problem ('Objectives' tab)
* Define domain
* Add context with any considerations

#### [2] Define objectives ('Objectives' tab)
* Generate suggested objectives
* Select relevant suggested objectives
* Add manual/custom objectives 
* Save selected options
* Edit objective properties
* Save objective definitions
###### OR ######
* Upload objectives csv file with columns objective_name, direction, aggregation, unit

#### [3] Define and score options ('Options' tab)
* Generate suggested options
* Select relevant suggested options
* Add manual/custom options 
* Save selected options
* Generate data collection plan to score options per objective
* Score selected options in table
* Save scored options
###### OR ######
* Upload scored options csv file with columns option_name, objective_X, objective_Y, etc.

#### [4] Run optimization ('Optimization' tab)
* Generate suggested approach 
* Select approach: binary or proportional selection _(see problem types and use cases below)_
    - If binary, specify exclusive (just one selected) or combination (multiple selected) of options
    - If proportional, specify minimum and maximum allocation range for selected options (each solution must sum to 100%)
* Select mode: fast speed (start to iterate) or thorough exploration (final results) _(see conceptual explainer below)_

#### [6] Interpret results ('Optimization' tab)
* Examine selected Pareto result list _(see conceptual explainer below)_
* Examine Pareto front charts of pair-wise objectives
* Download result csv _(optional)_
* Generate result explanation
* Examine result explanation

#### [7] Select solution ('Optimization' tab)
* Select solution(s)
* Provide feedback

### Use cases
#### When to use:
* [ ] Critical/valuable use case worth your time, ideally recurring (reuse)
* [ ] Multiple objectives with conflicting trade offs
* [ ] Many decision options to consider, often proportional (e.g. portfolio) or combinatorial (non-exclusive binary)
* [ ] Sufficient structured data to model and score options given objectives

#### Problem type overview

| Problem Type         | Domains                          | Optimization Approach  |
|----------------------|----------------------------------|------------------------|
| Portfolio management | finance, product, marketing      | Proportional           |
| Selection            | vendors, scheduling, tools       | Binary                 |
| Network planning     | logistics, facilities            | Binary (usually)       |
| Design               | engineering                      | Binary (usually)       |

#### Problem domain overview
COMING SOON

### Examples

You can use these examples in the app directly or as inspiration for your own problems. 

* **Select an AI model** _-> used when building this app!_
  - [Context](https://raw.githubusercontent.com/cafzal/decision_assist_examples/main/select_AI_model/context.txt)
  - [Objectives CSV](https://raw.githubusercontent.com/cafzal/decision_assist_examples/main/select_AI_model/objectives.csv)
  - [Scored Options CSV](https://raw.githubusercontent.com/cafzal/decision_assist_examples/main/select_AI_model/options.csv)
  – Approach: Binary (exclusive or combination)

* **Prioritize product features** _-> used when building this app!_
  - [Context](https://raw.githubusercontent.com/cafzal/decision_assist_examples/main/prioritize_product_features/context.txt)
  - [Objectives CSV](https://raw.githubusercontent.com/cafzal/decision_assist_examples/main/prioritize_product_features/objectives.csv)
  - [Scored Options CSV](https://raw.githubusercontent.com/cafzal/decision_assist_examples/main/prioritize_product_features/options.csv)
  - Approach: Proportional (min/max allocation = 10%/30%)

* **Balance an investment portfolio**
  - [Context](https://raw.githubusercontent.com/cafzal/decision_assist_examples/main/balance_investment_portfolio/context.txt)
  - [Objectives CSV](https://raw.githubusercontent.com/cafzal/decision_assist_examples/main/balance_investment_portfolio/objectives.csv)
  - [Scored Options CSV](https://raw.githubusercontent.com/cafzal/decision_assist_examples/main/balance_investment_portfolio/options.csv)
  - Approach: Proportional (min/max allocation = 2%/20%)

* **Buy a car**
  - [Context](https://raw.githubusercontent.com/cafzal/decision_assist_examples/main/other_examples/buy_a_car/context.txt)
  - [Objectives CSV](https://raw.githubusercontent.com/cafzal/decision_assist_examples/main/other_examples/buy_a_car/objectives.csv)
  - [Scored Options CSV](https://raw.githubusercontent.com/cafzal/decision_assist_examples/main/other_examples/buy_a_car/options.csv)
  - Approach: Binary (exclusive)

To use these examples:
1. Open the context file and copy its contents
2. In the Objectives tab:
   - Paste the domain name (e.g., "Select an AI model") in the Domain field
   - Paste the context text in the Context field
3. Download the objectives CSV file
4. Upload it in the Objectives tab
5. Download the corresponding options CSV file
6. Upload it in the Options tab
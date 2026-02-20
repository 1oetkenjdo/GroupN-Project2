# Project 2 – Concrete Mix Design Calculator  

**Client:** Nebraska Department of Transportation (NDOT)  
**Course:** CIVE 202  
**Group Members:** Jacob Oetken, Anicet Atikpohou, Abbas Bashir, and Michael Albracht

---

## What This Program Does

This Python program calculates material quantities for concrete mix designs. It determines how much of each ingredient (cement, aggregates, water, etc.) is needed to create exactly one cubic yard of concrete with specific properties.

**You can:**

- Enter your own custom mix design specifications
- View pre-calculated results for 4 real-world project mix designs
- See detailed weight summaries formatted for easy reading

---

## Getting Started

### Prerequisites

- **Python 3.x** installed on your computer
- A Python IDE or terminal/command prompt
- The program file: `GroupN_Project2_FINALCODE.ipynb` (Jupyter Notebook)

### How to Run the Program

#### Option 1: Using Jupyter Notebook (Recommended)

1. Open `GroupN_Project2_FINALCODE.ipynb` in VS Code or Jupyter
2. Run the cells in order from top to bottom
3. When prompted, enter your values (or skip to see pre-defined mix designs)

#### Option 2: Using Terminal/Command Prompt

1. Navigate to the project folder
2. Run: `python GroupN_Project2_FINALCODE.py` (if converted to .py)
3. Follow the on-screen prompts

---

## How to Use the Program

### Step 1: Understanding the Inputs

When you run the program, you'll be asked to enter **16 values**:

#### Material Weights (pounds per cubic yard)

- Cement weight
- Fly ash weight
- Silica fume weight
- Other supplementary cementitious material (SCM) weight

#### Mix Design Parameters

- Water/cement ratio (example: 0.45)
- Target air content percentage (example: 6.0)
- Fine aggregate percentage (example: 30)
- Coarse aggregate percentage (example: 70)
- Other aggregate percentage (example: 0)
  - **Note:** Aggregate percentages should add up to 100

#### Specific Gravity Values

- Cement specific gravity (typical: 3.15)
- Fly ash specific gravity (typical: 2.02)
- Silica fume specific gravity (typical: 2.23)
- Other SCM specific gravity (typical: 2.90)
- Fine aggregate specific gravity (typical: 2.68)
- Coarse aggregate specific gravity (typical: 2.62)
- Other aggregate specific gravity (typical: 2.55)
  - **Important:** All specific gravity values MUST be greater than zero otherwise a divide by zero error occurs

### Step 2: Entering Your Values

Example interaction:

| You See | You Input |
| ------- | -------- |
| Enter the weight of cement per cubic yard: | 496 |
| Enter the weight of fly ash in cubic yard: | 124 |
| Enter the weight of silica fume per cubic yard: | 0 |
| Enter the weight of SCM per cubic yard: | 0 |
| Enter the target water/cement ratio: | 0.423 |
| Enter the target % of air content: | 6.0 |
| Enter the target % of fine aggregate: | 30 |
| Enter the target % of coarse aggregate: | 70 |
| Enter the target % of other aggregate: | 0 |
| Enter the specific gravity of cement (MUST BE NON ZERO): | 3.15 |
| [...continues for remaining inputs...] | - |

---

### Step 3: Reading Your Results

The program will display a formatted summary:

```text
-----------------------------------------
  User Input Mix Design – Weight Summary
      (1 Cubic Yard of Concrete)
-----------------------------------------
Cementitious Materials:
  Cement:                496.00 lb
  Fly Ash:               124.00 lb
  Silica Fume:             0.00 lb
  Other SCM:               0.00 lb
-----------------------------------------
Aggregates:
  Fine Aggregate:       1234.56 lb
  Coarse Aggregate:     2876.54 lb
  Other Aggregate:         0.00 lb
-----------------------------------------
  Total Mass:           4000.00 lb/yd³
  Water:                 262.00 lb
-----------------------------------------
```

---

### Step 4: Viewing Pre-Defined Mix Designs

After your custom input, the program automatically displays **4 additional mix designs** based on real mix designs and projects. **You don't need to do anything** - they run automatically:

1. **Mix Design 1** - LF4500 Footing Mix (Eppley Terminal Entrance)
2. **Mix Design 2** - OPW4000 Hand-Placed (Eppley South Parking)
3. **Mix Design 3** - OPW4000 Slipform Paver (Eppley South Parking)
4. **Mix Design 4** - L6 1/2 PAE (Eppley Ramp Taxilane)

---

## Understanding the Results

### What the Numbers Mean

Each output shows:

- **Cementitious Materials**: Binding agents (cement, fly ash, etc.) that hold concrete together
- **Aggregates**: Sand and gravel that provide bulk and strength
- **Water**: Required for hydration and workability
- **Total Mass**: Combined weight of all materials (typically 3,600-4,200 lb/yd³)

### How the Calculation Works

The program uses the **Absolute Volume Method**:

1. Converts your material weights to volumes using specific gravity
2. Calculates how much space remains after accounting for cement, water, and air
3. Fills remaining space with aggregates according to your percentages
4. Converts aggregate volumes back to weights

---

## Tips for Using the Program

### Do's

- **Ensure the specific gravities are non zero** (or the program will crash)
- **Make sure aggregate percentages add to 100** (30% + 70% + 0% = 100%)
- **Use realistic water/cement ratios** (typically 0.3 to 0.6)
- **Keep air content between 4-8%** for most applications

### Don'ts

- Don't enter letters or symbols when numbers are expected
- Don't use zero for specific gravity values
- Don't skip any input prompts or the program will fail
- Don't expect validation - the program will calculate whatever you enter

---

## Common Issues and Solutions

| Problem | Solution |
| ------- | -------- |
| "ValueError: could not convert string to float" | You entered text instead of a number. Re-run and enter only numbers. |
| "ZeroDivisionError" | You entered 0 for a specific gravity. All SG values must be greater than zero. |
| Results look unrealistic | Check that aggregate percentages sum to 100 and SG values are reasonable. |
| Program won't run | Make sure Python 3.x is installed and you're in the correct directory. |

---

## What's Included

### Pre-Defined Mix Designs

The program includes 4 real-world mix designs from NDOT projects:

**Mix 1 – Eppley Terminal Entrance (LF4500 Footing)**  

- 496 lb cement + 124 lb fly ash
- 6% air content
- 30% fine / 70% coarse aggregate split

**Mix 2 – Eppley South Parking Phase 2 (Hand-Placed OPW4000)**  

- 611 lb cement (no fly ash)
- 7% air content
- 38% fine / 62% coarse aggregate split

**Mix 3 – Eppley South Parking Phase 2 (Slipform OPW4000)**  

- 611 lb cement (same as Mix 2)
- Lower water/cement ratio (0.37 vs 0.41)
- 7.5% air content

**Mix 4 – Eppley Ramp Taxilane (L6 1/2 PAE)**  

- 611 lb cement
- 5.6% air content
- Inverted proportions: 70.3% fine / 29.7% coarse

---

## Project Documentation

For more detailed information, see:

- **ACD.md** - Annotated Code Document (engineering focus)
- **Technical_Code_Explanation.md** - Line-by-line code walkthrough
- **GroupN_Project2_FINALCODE.ipynb** - The main program file

---

## Need Help?

### Quick Troubleshooting

1. Make sure Python 3.x is installed: Run `python --version` in terminal
2. Make sure you're in the correct directory
3. Check that all input values are numbers (no letters or symbols)
4. Verify specific gravity values are all > 0

### Contact

For questions about this project, contact any group member listed at the top of this document.

---

## Technical Notes

### Requirements

- **Python:** Version 3.x or higher
- **Libraries:** None (uses only built-in Python functions)
- **Input Format:** Float values (decimals accepted)

### Assumptions

- Specific gravities must be non-zero
- Aggregate percentages should sum to 100%
- Water/cement ratio is applied to total cementitious material
- Total volume equals 27 cubic feet (1 cubic yard)

### Limitations

- No input validation (accepts any numeric value)
- No error handling for invalid inputs
- Does not automatically enforce percentage sum requirements
- Results are displayed only (not saved to file)
- No graphical user interface

### Future Enhancements

- Add input validation checks
- Implement error handling for common mistakes
- Export results to CSV or Excel automatically
- Create a web-based interface
- Add data visualization of mix proportions

---

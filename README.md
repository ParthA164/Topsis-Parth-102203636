# TOPSIS Implementation in Python

## About TOPSIS
TOPSIS (Technique for Order of Preference by Similarity to Ideal Solution) is a multi-criteria decision analysis method which was originally developed by Hwang and Yoon in 1981. TOPSIS chooses the alternative that is the closest to the positive ideal solution and farthest from the negative ideal solution.

## Installation

```bash
pip install topsis
```

## Usage
The program accepts the following arguments:
1. Input file (.csv)
2. Weights (comma-separated)
3. Impacts (comma-separated)
4. Output file (.csv)

```bash
python topsis.py input.csv "1,1,1,2,2" "+,-,-,+,-" output.csv
```

## Input File Format
Input file must contain three or more columns:
* First column: Object/Variable name
* Second to last columns: Criteria values
* File must be a CSV file (.csv extension)

Sample input file:
```csv
Fund Name,P1,P2,P3,P4,P5
M1,0.68,0.48,13.07,0.74,0.87
M2,0.78,0.61,14.85,0.71,0.29
M3,0.61,0.37,14.01,0.71,0.95
M4,0.76,0.39,11.11,0.77,0.14
M5,0.59,0.41,11.32,0.82,0.55
```

## Output Format
Output file contains all the columns of input file along with two additional columns having normalized scores and ranks.

Sample output file:
```csv
Fund Name,P1,P2,P3,P4,P5,Topsis Score,Rank
M1,0.68,0.48,13.07,0.74,0.87,0.7722,2
M2,0.78,0.61,14.85,0.71,0.29,0.6253,4
M3,0.61,0.37,14.01,0.71,0.95,0.8231,1
M4,0.76,0.39,11.11,0.77,0.14,0.5486,5
M5,0.59,0.41,11.32,0.82,0.55,0.6791,3
```

## Parameters

### Weights
Weights indicate the relative importance of each criterion. They should be provided as comma-separated values. Number of weights should be equal to number of criteria.

Example: `"1,1,1,2,2"`

### Impacts
Impacts decide whether the criterion is to be maximized (+) or minimized (-). They should be provided as comma-separated values. Number of impacts should be equal to number of criteria.

Example: `"+,-,-,+,-"`

## Error Handling
The program handles the following errors:
* Input file does not exist
* Input file is not a CSV file
* Input file has less than 3 columns
* Number of weights, impacts is not equal to number of criteria
* Impacts are not either '+' or '-'
* Non-numeric values in criteria columns

## Example
Consider a real estate decision problem with the following criteria:
1. Cost (-)
2. Square footage (+)
3. Distance to city center (-)
4. Age of building (-)
5. Number of rooms (+)

```bash
python topsis.py houses.csv "0.25,0.25,0.15,0.15,0.20" "-,+,-,-,+" output.csv
```

## Dependencies
* Python 3.x
* Pandas
* NumPy

## License
This project is licensed under MIT License - see the LICENSE file for details.

## Contributing
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request


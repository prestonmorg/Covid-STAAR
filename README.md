# COVID-19's Impact on the Algebra I STAAR Passing Rates

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/prestonmorg/Covid-STAAR/blob/main/notebooks/Covid_STAAR_Notebook.ipynb)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

This analysis investigates the COVID-19 pandemic's impact on the passing rates of the Algebra I STAAR (State of Texas Assessments of Academic Readiness) test both in the years prior to and following the pandemic. 

## Installation and Setup
There are two ways to access the analysis provided in this repository. One way is running this locally with Python, and the other way is running this directly through Google Colab. The processes for accessing both methods are outlined below.

### Method 1 - Running Locally
1. **Clone the Repository**
```bash
git clone [https://github.com/prestonmorg/Covid-STAAR.git](https://github.com/prestonmorg/Covid-STAAR.git)
cd Covid-STAAR
```
2. **Set Up a Virtual Environment (Recommended)**
```bash
# macOS/Linux
python3 -m venv venv
source venv/bin/activate

# Windows
python -m venv venv
venv\Scripts\activate
```
3. **Install Dependencies**
```bash
pip install -r requirements.txt
```
4. **Launch the Notebook**
```bash
jupyter notebook notebooks/Covid_STAAR_Notebook.ipynb
```
### Method 2 - Run in Google Colab
If you prefer to run the notebook directly in Google Colab as opposed to setting anything up locally:
1. Click the ![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg) badge at the top of this page.
2. Select **Runtime > Run all** in the top menu.

Note that there is no need to upload the data used in this project to your active Colab runtime session files since the data is read directly from this GitHub repository.

## Data Collection and Cleaning

### Data Source
The source for this data came from the [Texas Assessment Research Portal](https://txresearchportal.com/selections?tab=state). Specific steps for collecting this data are outline below.

1. Select the **STAAR EOC** program.
2. Select the **Group Summary: Performance Levels and Reporting Categories** report.
3. Select each administration in the form of **Spring ____**.
4. Select the **Algebra I** subject.

There are a few things to note. One is that the administration that was chosen (i.e. choosing the Spring administration for each year) was done so to account for when most students would take the EOC (end of curriculum) STAAR test. There are students that can pass through necessary Algebra I credit oustide of the normal school timeline, like in Summer, Fall, or Winter. Another thing to note is that this same data is accessible for other subjects as well. In the 'STAAR_Cumulative_Scores.csv' file, you'll notice that Algebra I is not the only subject listed. This is something I will talk about later on in the page about future projects that could stem from this analysis.

### Data Cleaning
There were only two main things that needed to be cleaned/processed from the 'STAAR_Cumulative_Scores.csv' file that was obtained using the steps mentioned above. All of the cleaning steps mentioned were done manually.

The first (and simplest) cleaning piece was only taking the Algebra I scores from the file. Due to how to the file is presented (alphabetically), Algebra I is the first test listed and was the easiest to find. Another important thing to note is that I did not include the scores from the STAAR A and STAAR L tests. The main reason for this is that there were only 2 Spring administrations in which the STAAR A test had scoring data on, and only 5 Spring administrations in which the STAAR L test had scoring data. Due to the inconsistency of the provided data, I decided it was best to note include these metrics in the final cleaned dataset.

The second (and more involved) cleaning piece was relating the scoring metrics from 2012-2016 and 2017-2025 (excluding the year 2020 since there were no STAAR tests that year). 

The scoring metrics for the timeline of 2012-2016 were as follows:
1. Satisfactory
2. Advanced
3. Unsatisfactory

The scoring metrics for the timeline of 2017-2025 were as follows:
1. Did Not Meet
2. Approaches
3. Meets
4. Masters

To bridge the two timelines into one, I ended up making 3 scoring metrics:
1. Unsatisfactory - This included the **Did Not Meet** and the **Unsatisfactory** groups from the different timelines.
2. Approaches to Meets - This included the **Satisfactory**, **Approaches**, and **Meets** groups from the different timelines.
3. Advanced - This included the **Satisfactory** and the **Masters** groups from the different timelines.

I did it this way to make sure there was an easy distinction between passing and failing, while also accounting for an 'Advanced' section to list the number of students who excelled on the test.

One final thing to note is that the STAAR data given from the website has a strange format of only providing counts/percentages for 'X and Above' for every group that isn't the top scoring group from that timeline. However, it was quite easy to work backwards and grab the specific numbers from the strangely formatted data.

## Results and Findings

TBA

## Future Projects



## Acknowledgements and References



## Licenses
This project is open-source and available under the [MIT License](LICENSE).

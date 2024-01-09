# Process Mining with East Midlands Ambulance Service (EMAS).
## NHS England Digitial Analytics and Research Team - PhD Internship Project

### Alex Coles, Paul Carroll, Martina Fonseca - June 2023 - Nov 2022

[![status: experimental](https://github.com/GIScience/badges/raw/master/status/experimental.svg)](https://github.com/GIScience/badges#experimental)


#### Overview
Process Mining is the term given to a family of techniques that have been developed to analyse these records events and process flows, Van Der Aalst et al (2012). 
Process Mining has three main application areas, these are discovery, conformance checking and enhancement. In process discovery, the output is a fact-based process model based on the recorded events in the database. Discovery is the most common process mining investigation, where the discovered process model is often not expected by the supervisor of the process. In conformance checking we measure how well the recorded processes fit a pre-defined process model. Conformance-checking techniques can therefore be used to check whether certain rules and policies are being abided by within an organisation. Finally, enhancement is focused on improving the existing process models by analysing how additional attributes affect the throughput times and frequencies of activities in the process. 

All process mining techniques require an event log to start. An event log is a sequential recording of the events or activites that happened to a particular case (the person or object travelling through the process) with the associated time stamps of the events. Additional attributes for cases or individual events such as the resource responsible for performing the activity on the case allow additional analysis of the effect the attributes have on the process but are not essential to start process mining. The EMAS data that was worked with in this repo, was transformed from the reported dataset into an event log, for use with the process mining techinques. In this repo, we've created a fake dataset that resembles the setup of Ambulance service data. This can be created using the fake data generator workbook, and transformed into an event log using the event log workbook. 

With all these requirements and concerns in mind, a few methodologies have been created to aid the adoption and use of process mining within organisations. The most well-known are the L* and PM2 methodologies Aalst (2011), Van Eck et al (2015). Both methodologies describe a similar approach to conducting a process mining project. 


#### Walkthrough 

The project began with EMAS stakeholders keen to explore what process mining could do with their data. 
Could it shine a light on their processes, could it inform hidden parts of their processes, could it identify bottlenecks, and could it help drive efficiencies within the Service. 

Initially the dataset required a lot of expert explanation, and this became normal throughout the process. Another tenet of process mining is to engage with subject matter experts on an iterative process, showing the experts outputs directly from the data, asking them if this matches their understanding of how processes work, and if the data is correct. 
A first examination of the data showed the need for business rules to be established. As a process map didn't already exist, for the data to make sense this had to be established. Some data was misreported, there were unnecessary events, and as with any raw dataset, there were some data quality issues. 
Subject matter experts at EMAS were able to help with the business rules, and with defining the processes. The business rules were built out, and extended to discard some events that we wanted to exclude from the event log. This doesn't mean these were discarded completely, but for the event log purposes, they were redundant. This data was kept and used later on in the processes. It has a huge value in the iterative processes employed later on. 

We then began identifying the DFGs (Directly Follows Graphs) for the highest occuring processes. The top two occuring processes accounting for 99% of the Job Cycle traces. 
Conformance techniques were used to measure how well the mined process models fitted the event log data. However, the variation in the treatment activites also casued the mined models to allow events including the call for an ambulance to happen in a sequence counterintuitive to real ambulance job cycles. 

A succession of further process mining techniques were then applied to the data. A majority of these involved enriching the data, the iterative process around adding data to the event log to find out more about it. This is especially important with event logs where two processes account for such a high percentage of cases, 99%. With Ambulance service being temporal, of the seven processes in the DFG, all had to happen sequentially. The enrichment of the data, adding in IMD data, but also adding back in some of the original patient level data, allowed for patterns, differences in means, and other explorations of data to take place. 

Lastly machine learning was applied to see if outcomes could be predicted. Please see the report for full details. 

_**Note:** Only public or fake data are shared in this repository._


#### Project Stucture

- The main code is found in the root of the repository (see Usage below for more information)
- The workbooks are set up and numbered sequentially. We would suggest running through them in this order. 
- The accompanying [report](./reports/report.pdf) is also available.
- More information about the code usage can be found in the [model card](./model_card.md)
- {OTHER REPO STRUCTURE}
- 
This repository holds code for the Process Mining with EMAS project. 
This project was undertaken in collaboration with East Midlands Ambulance Service Data, and built within their IG area using their data. 
The data within this repo is fake data, generated from the fake data generator workbook. It resembles EMAS data in form, but is completely fake.

[Link to original project propsoal](https://nhsx.github.io/nhsx-internship-projects/)

### Built With

[![Python v3.10](https://img.shields.io/badge/python-v3.10-blue.svg)](https://www.python.org/downloads/release/python-3100/)
- PM4PY

### Getting Started

#### Installation

To get a local copy up and running follow these simple steps.

To clone the repo:

`git clone https://github.com/nhsx/{REPO NAME}`

To create a suitable environment:
- ```python -m venv _env```
- `source _env/bin/activate`
- `pip install -r requirements.txt`

{ADDITIONAL TECHNICAL SUPPORT AND NEEDS} 

### Usage
{DESCRIPTION OF CODE}

#### Outputs
{LIST AND DESCRIPTION OF OUTPUTS}

{NOTES ON REPRODUCIBILITY OF RESULTS}

#### Datasets
{DESCRIPTION AND LINKS TO DATASETS}

{LINK TO FAKE DATA TO SUPPORT INITAIL CODE RUNS}

### Roadmap

See the {LINK TO REPO ISSUES} for a list of proposed features (and known issues).

### Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

_See [CONTRIBUTING.md](./CONTRIBUTING.md) for detailed guidance._

### License

Unless stated otherwise, the codebase is released under [the MIT Licence][mit].
This covers both the codebase and any sample code in the documentation.

_See [LICENSE](./LICENSE) for more information._

The documentation is [© Crown copyright][copyright] and available under the terms
of the [Open Government 3.0][ogl] licence.

[mit]: LICENCE
[copyright]: http://www.nationalarchives.gov.uk/information-management/re-using-public-sector-information/uk-government-licensing-framework/crown-copyright/
[ogl]: http://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/

### Contact

To find out more about the [Digitial Analytics and Research Team](https://www.nhsx.nhs.uk/key-tools-and-info/nhsx-analytics-unit/) visit our [project website](https://nhsx.github.io/AnalyticsUnit/projects.html) or get in touch at [analytics-unit@nhsx.nhs.uk](mailto:analytics-unit@nhsx.nhs.uk), or contact [Paul Carroll](Paul.Carroll9@nhs.net)

<!-- ### Acknowledgements -->


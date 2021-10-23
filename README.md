# hackathon-hack-the-fall
project gallery of the hack-the-fall


Inspiration
We want to make change in the society by motivating the depressed people and by strengthening them mentally.

What it does
Azure Sentinel Automated Threat-Informed Defense Assessment Tool helps you(assume that you are in a depressed state) by connecting you to the people who are mentally strong and who are willing to help you and listen to you .It provides a platform where you can express your feelings without providing any of your identity.

Azure Sentinel covered MITRE tactics and Techniques by Analytics and Hunting queries (A Coverage Score)
Related Azure native security controls, D3FEND defenses, NIST mitigations, Atomic Tests, Sigma Rules etc...
The project goes through the following steps:

Threat Profiling
The first step is to provide the tool with a threat profile. The threat profile is represented as MITRE ATT&CK navigation layer. The infosec community already shares many navigation layers of threat profiles and mapped threat intelligence reports. One of them is the following:

DeTTECT Threat Actors Navigation Layers
Further more the tool can help you generate a unified threat profile based on your geo-location and Industy. The available Coutries/regions and Sectors can be found in 'Resources/APT-groups.xlsx'

Azure Sentinel Analytics and Hunting Query Coverage
Once a threat heatmap is created. The tool connects to your Azure Sentinel environment and extracts the covered ATT&CK tactics and techniques automotically by your analytics and hunting queries. A coverage navigation layer will be created and exported as json a file that you can view using the MITRE ATT&CK navigator. The Coverage layer can be found in 'Reports/Coverage_layer.json'

Gap Analysis and Related Recommendations
In this step, the tool performs a gap analysis against the threat profile and generates a detecion gap matrix (navigation layer). Based on the gap matrix, the tool will provide you with the following:

The Azure Native Security controls that can help you prevent and detect the threat tactics and techniques
The related NIST mitigations to help you mitigate the threat actors techniques
The related MITRE D3FEND artifacts and defenses
A list of recommended publically available SIGMA rules that you can rapidly use and deploy to detect the watched threat techniques
A list of recommended publically available Atomic tests that you can emulate to help you develop the needed detection rules/analytics and threat hunting queries.
Reporting
The previously discussed sections will be generated as a Web report and excel file to help you align your operations to the MITRE ATT&CK framework and track your enhancements.

How we built it
This project was built with Python3. In order for it to successfully generate the coverage score and the recommendations, two main pieces of information needed to be extracted. First information is the threat profile/actor TTPs. The defender provides a threat profile as a MITRE ATT&CK navigation layer. Thus, a json parsing function will extract the specific TTPs. The 2nd information is the techniques covered by Azure Sentinel Analytics (Detection Rules) and Hunting Queries. This, can be done thanks to Azure Sentinel API. Hunting techniques are provided by the API but the Analytic Techniques are extracted using a naming convention. In our case extracting them from the rule name T+ an ID e.g: T1003.001 - LSASS Memory (the tool will extract T1003.001). Once we have the TTPs used by the Threat actors and the techniques covered by Azure Sentinel, the tool will identify the TTPs to focus on (what Azure Sentinel is not able to detect/hunt yet) or what we call the detection gaps. Based on the uncovered techniques, the project will provide the related Azure Native Security controls, D3FEND defenses, the related SIGMA rules, the related Atomic tests that you can use to prevent and detect the threat TTPs. All the results are presented as different format reports (Web and Excel) and helpful navigation layers (Coverage layer,Threat profile Layer etc.). TTPs and threat actor details were extracted from MITRE live servers and official documents.

Challenges we ran into
Many Challenges were faced. Some of them are the following:

How to correlate information from different sources
How to identify the target countries and sectors from texts (we managed to add them manually eventually)
How to parse different format of files and filter the required details
Accomplishments that we're proud of
We completed the project and we didn't surrender

What we learned
We learned:

How to interact with different sources of information
How to align SOC operations with MITRE ATT&CK Framework
How to create a threat profile
What's next for Automated Threat-Informed Defense Assessment Tool
Publish it as an open source project
Add more threat actor details
Built With
azure-sentinel-api
mitre
python

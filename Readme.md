# Cyber Career Advisory Dashboard
Empowering cyber career advisors with real-time job market insights using Power BI.

## Project Description
The **Cyber Career Advisory Dashboard** is designed to help cyber career advisors in educational institutions guide students and recent graduates more effectively by providing real-time, data-driven insights into job market trends, in-demand skills, and industry demands. 

By centralizing fragmented job market data, this Power BI solution ensures that career advice is current, relevant, and aligned with industry needs.

##  Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Dashboard Preview](#dashboard-preview)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

##  Installation
1. Clone the repository:
   
   git clone https://github.com/Lokenderyadav/Team-9-Cyber-Career.git
   cd Career-Advisory-Dashboard
   

2. Set up a virtual environment if using Python scripts for ETL:
   
   python -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   

3. Open the Power BI `.pbix` file in Power BI Desktop.

4. Ensure data sources (e.g., job board APIs, CSVs, or SQL Server) are configured and credentials are set.

## Usage
1. Load the dashboard in Power BI Desktop or publish to Power BI Service.
2. Use slicers to filter by job roles, industries, salary ranges, or skills.
3. Generate exportable reports for student advising sessions.


# If applicable, run data pipeline scripts (example)
python extract_jobs.py
python transform_skills.py


## Features
- Real-time job trend visualization
- In-demand skill analysis (technical + soft)
- Salary benchmarks across roles & industries
- Industry-wise hiring activity breakdown
- Interactive filters, timelines, and role-based insights
- Exportable reports for advisor-student meetings

## Dashboard Preview
[![Dashboard Screenshot](images/dashboard-preview.png)](we will update once we publish)

## Project Structure

Career-Advisory-Dashboard/
├── data/                     # Raw and processed data
├── src/                      # Python ETL scripts (if used)
├── dashboard/                # Power BI .pbix file
├── images/                   # Screenshots for documentation
├── README.md
└── LICENSE


## Contributing
Pull requests are welcome! For major changes, please open an issue first to discuss what you'd like to change.

## License
MIT License. See [LICENSE](LICENSE) for details.

## Acknowledgements
- [Microsoft Fabric Community](https://community.fabric.microsoft.com/)
- [Marty Nemko – Career Counseling](https://www.martynemko.com/)
- [Jeffrey Poulos – Future of Career Advising](https://www.linkedin.com/pulse/future-career-advising-jeffrey-poulos-m-a-cprw-n5lpe)

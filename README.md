# Cloud Database for Market Analysis of Electric Vehicle Powertrain Components

- 🌐 [Project page](https://github.com/nikolailen/gcp-ev-powertrain-database/blob/main/high_overview_presentation_git.pdf)
- 👤 Project contact: [Nikolai Len](https://www.linkedin.com/in/niklen/)

## Project Overview

This project aims to develop an advanced cloud-based database for analyzing the market of electric vehicle powertrain components. The database is designed to provide insights into global vehicle sales and powertrain components, offering detailed analysis based on various electrification types, regional distributions, and market share distributions among suppliers.

## Project Objectives

### Conceptual Aspects

- **Initial Position**: Utilize a third-party database, which contains volumes for global vehicle sales.
- **Enhancement**:
  - Inclusion of powertrain components data for each car model.
  - Pricing details for each component.
  - Supplier information for each component.
  - Addressability analysis for competing suppliers.

### Technical Aspects

- **Concept**: Develop a scalable database on Google Cloud Platform (GCP) using advanced cloud technologies, allowing seamless updates through Google Sheets integration.
- **Development Steps**:
  1. Conceptualize the GCP project.
  2. Obtain security approvals.
  3. Collaborate with IT to configure GCP elements.
  4. Establish Cloud Storage for data management.
  5. Develop Colab Enterprise notebooks for data processing.
  6. Upload and finalize the database in BigQuery.
  7. Link BigQuery with Looker Studio for dashboard creation.
  8. Automate updates using Cloud Functions.
  
## Hierarchical Scheme of electric vehicle powertrain components

The database categorizes electric vehicle powertrain components into four hierarchical levels:

1. **Level 1**: Voltage Type
2. **Level 2**: Product Type
3. **Level 3**: Product Subtype
4. **Level 4**: Product Rank

## Database Elements

- **Value List (VL)**: Details all potential vehicle architectures and powertrain components.
- **Power Schedule (PS)**: Provides formulas for calculating component power.
- **Supplier Dictionary (SD)**: Maps suppliers to vehicle models and powertrain components.
- **Price List (PL)**: Lists prices of powertrain components based on power and voltage.

## Workflow Overview

### 1. Google Sheets Updates
- Marketing specialists update Google Sheets with the latest data (Value list, Power schedule, Supplier dictionaries, Component prices).
- Updated sheets are automatically copied to GCP Cloud Storage via API.

### 2. Execution of Colab Enterprise Scripts
- **Cleaning**: Preprocesses uploaded files.
- **Merging**: Combines various datasets (PIHS, VL, PS, SD) using custom scripts.
- **Transformation**: Reorganizes and finalizes the database structure.

### 3. Integration with BigQuery
- Pre-processed CSV files are uploaded to BigQuery.
- Queries are executed to merge the database with pricing and addressability tables.
- The final database is connected to Google Sheets and Looker Studio for visualization.

## Repository Structure

The repository contains nine notebooks:

- **00 Master Notebook**: This is the primary notebook that controls the execution of the entire workflow. Running this notebook sequentially launches the execution of all other notebooks in the repository.
- **01 to 09 Notebooks**: These notebooks perform specific tasks such as data cleaning, merging datasets, calculating component power, and finalizing the database structure. They are designed to be executed in sequence as directed by the master notebook.

## Deployment

The prepared database enables team members to independently access and analyze data through Looker Studio and Google Sheets, providing valuable market insights for strategic decisions.

## Technology Stack

- **Google Cloud Platform (GCP)**
- **BigQuery**
- **Looker Studio**
- **Google Sheets**
- **Colab Enterprise**

For more information, please refer to the [PDF presentation](high_overview_presentation_git.pdf) available in this repository.

## License

This project is licensed under the [MIT License](LICENSE).



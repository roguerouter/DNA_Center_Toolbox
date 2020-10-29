# DNA Center toolbox

*Scripts to work with DNA Center API and pull data.  DNA Center Toolbox will continue to expand and add new features over time.  A list of current features and functionality can be found below*

---

## Features

The current features of DNA Center Toolbox are as follows:

- Get Configuration Template list. 
- Download Configuration templates.  

Both commands can list all available templates or specific templates when an templateId is specified.

Future features to include working with command runner.

## Technologies & Frameworks Used

This is Cisco sample code written with Python3 that allows you to work with the DNA Center Appliance API.  Currently the sample code allows you to get templates and download templates from the API.

**Cisco Products & Services:**

- DNA Center

## Usage

Usage: dna_center_toolbox.py [OPTIONS] COMMAND [ARGS]...

Options:
  --allid       Request all configuration templates from DNA Center appliance
                (DEFAULT)
  --cfgid TEXT  Request configuration template for specific ID from DNA Center
                appliance
  --help        Show this message and exit.

Commands:
  dwnld-templates
  get-templates

Example 1.) ./dna_center_toolbox.py get-templates

- Will list all available configuration templates from DNA Center on the command line.  A user can then find the templateId of the template they want more details about.

Example 2.) ./dna_center_toolbox.py --cfgid 47bcb0db-49ff-4bce-b47e-2f788eaff144 get-templates

- Will list specific configuration template details from DNA Center on the command line.  The ID can be obtained by running ./dna_center_toolbox.py get-templates and looking in the output for the templateId for the configuration template you want more details about.

Example 3.) ./dna_center_toolbox.py dwnld-templates

- Will download ALL configuration templates and place them in a folder named ./config-templates.  Each file will be listed by its template name and timestamp.  This will allow you to save and compare templates.

Example 4.) ./dna_center_toolbox.py --cfgid 47bcb0db-49ff-4bce-b47e-2f788eaff144 dwnld-templates

- Will download the specific configuration templates for the id entered.  The file will be placed in a folder named ./config-templates.  The file will be saved with its template name and timestamp to allow saving and comparison.

## Installation

Users can either clone from this Github repository or download the contents in a zip file by selecting the Green Clone or Download file near the top of the repository.  Choose a directory to clone or unzip the contents of the repository.  Before using the tool you will need to edit the dna_center_toolbox.py file and set DNAC_SERVER_IP = 'set_your_ip_here' to the ip address your DNA Center appliance.  Additionally, if you have valid certificates configured for your DNA Center and have the CA available on the local system you can change set DISABLEINSECUREWARNINGS = False.  Setting DISABLEINSECUREWARNINGS = False will force the URL lookup to verify certificates and the program will fail if certicates cannot be verified.

## Authors & Maintainers

- Matt Leuschner <mleuschn@cisco.com>

## License

This project is licensed to you under the terms of the [Cisco Sample
Code License](./LICENSE).

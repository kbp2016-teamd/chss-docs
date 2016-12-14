# CHSS Expert Medical System

## Overview
The CHSS project relies on the assumption that community healthcare
workers will be basically skilled to perform essential medical
diagnostics to test for a variety of common, serious ailments. This
is as a preventative measure to help prevent serious issues later
on, as well as a means to assist with decongesting healthcare
facilities further downstream.

In order to support this, the system requires an
[expert system](https://en.wikipedia.org/wiki/Expert_system) to aid
the community healthcare worker in diagnosing the likely issues a
patient is facing, and whether or not they need to visit the clinic.

## Prevalent Health Issues
As per the [leading causes of death in South Africa](http://www.statssa.gov.za/?page_id=737&id=3)
(data from Stats SA), the following diseases are targeted for the
minimum viable product (MVP) CHSS:

1. Infectious and parasitic diseases, such as tuberculosis and HIV.
2. Circulatory system diseases, such as heart disease and strokes.
3. Respiratory diseases, such as influenza and pneumonia.

These issues accounted for approximately 40% of all deaths in
South Africa in 2013.

## Questions
### Personal Information
The following personal information needs to be asked of a user when
they are first enrolled into the system:

| Field | Type | Details/Notes |
| ----- | ---- | ------------- |
| First name | `string` |   |
| Last name | `string` |   |
| ID number | `string` | The patient's ID number |
| Address | `string` | Where the patient lives |
| Gender | `char` | `m` or `f` |
| Date of birth | `date` | Used to determine patient's age |

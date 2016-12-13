# Community Healthcare Support System

## Overview
This repository contains documentation for the **Community Healthcare
Support System** - a project as part of the
[Kent Beck Project](http://kbp.jcse.org.za/).

The project aims to provide software to assist community healthcare
workers (the envisaged first line of support in the
[National Health Insurance](http://www.gov.za/about-government/national-health-insurance)
scheme).

## Components
The software system consists of several components:

* A [Data Collection API](https://github.com/kbp2016-teamd/chss-api) to
  provide data storage and functionality.
* An [Android application](https://github.com/kbp2016-teamd/chss-workerapp)
  to be used by the community healthcare workers themselves while out
  in the field.
* A [Java-based client library](https://github.com/kbp2016-teamd/chss-java-client)
  for integrating the Android application (or any other Java-based
  application) with the API.
* A [web-based management interface](https://github.com/kbp2016-teamd/chss-web-ui)
  for data visualisation.
* An [Analytics API](https://github.com/kbp2016-teamd/chss-analytics-api)
  for performing calculations and providing data to the management
  interface.

## Documentation Guide
The following documentation is available in this repository:

* The [Data Collection API specification](api/collection-api-v1.raml),
  in [RAML](http://raml.org/) format.

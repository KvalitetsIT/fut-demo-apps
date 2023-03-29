# FUT Demo Apps
Apps that demonstrate the use of the [eHealth Infrastructure](https://ehealth-dk.atlassian.net/wiki/spaces/EDTW/overview). The infrastructure API is based on the [FHIR](https://fhir.org/) specifications. The demo apps follow the Backend for frontend (BFF) pattern. Backend projects are based on Java Spring Boot and frontend projects are based on React. The Java projects utilizes the [HAPI FHIR](https://hapifhir.io/) Java client library for communicating with the eHealth Infrastructure REST servers.

## List of apps
- [FUT Patient Demo BFF](https://github.com/kvalitetsIT/fut-patient-bff)
- [FUT Patient Demo Web App](https://github.com/kvalitetsIT/fut-patient-web)
- [FUT Administration Demo BFF](https://github.com/kvalitetsIT/fut-medarbejder-bff)
- [FUT Administration Demo Web App](https://github.com/kvalitetsIT/fut-medarbejder-web)

### FUT Patient Demo
The FUT Patient Demo demonstrates retrieving and displaying [Questionnaries](https://www.hl7.org/fhir/questionnaire.html) and sending [QuestionnarieResponse](https://www.hl7.org/fhir/questionnaireresponse.html).

### FUT Administration Demo
The FUT Administration Demo demonstrates retrieving Episodes of Care, Patients, Tasks, creating consent, creating CarePlans, among other things.

## Try it out
This repository contains a `docker-compose.yml` that makes it easy to try out the projects. All repositories and docker images are public. Use `docker-compose up`, and you can try the apps on the following ports:
- http://localhost:3001 (the patient web app)
- http://localhost:3002 (the administration web app)

## Interactions implemented
The patient demo applications roughly implements the [The Patient Care Plan in operation](http://ehealth-documentation.s3-website-eu-west-1.amazonaws.com/latest-released/sparx/EARoot/EA6/EA3/EA2/EA560.png) interactions, except all Questionnaries are always listed regardless of the responses already submitted.

The administration demo applications implement the following:
- Registering Episode of Care and giving Consent for a patient. See [this interaction diagram](http://ehealth-documentation.s3-website-eu-west-1.amazonaws.com/latest-released/sparx/EARoot/EA6/EA3/EA3/EA576.png).
- Applying Care Plan to Patient. [Interaction diagram](http://ehealth-documentation.s3-website-eu-west-1.amazonaws.com/latest-released/sparx/EARoot/EA6/EA3/EA3/EA578.png).
- Some parts of [Evaluation of Measurements](http://ehealth-documentation.s3-website-eu-west-1.amazonaws.com/latest-released/sparx/EARoot/EA6/EA3/EA3/EA580.png) have also been implemented.

## Recommended reading
This [high level process overview](https://ehealth-dk.atlassian.net/wiki/spaces/EDTW/pages/280559617/High+Level+Business+Flow) illustrates some of the core functionality of the infrastructure platform.

A central part of the implementation concerns the [switching of context](https://ehealth-dk.atlassian.net/wiki/spaces/EDTW/pages/270991361/Switching+Context), which is a security mechanism for granting access to relevant resources through the use of access tokens. Different resources and interactions require [specific contexts](https://ehealth-dk.atlassian.net/wiki/spaces/EDTW/pages/1695842461/Access+Control+in+eHealth+Services) depending on the type of user in question.

Technical documentation on creating CarePlans and Episodes of Care:
- [Enrolling a Patient in an Episode Of Care](https://ehealth-dk.atlassian.net/wiki/spaces/EDTW/pages/1662025729/Enrolling+a+Patient+in+an+Episode+Of+Care)
- [Creating Care Plans](https://ehealth-dk.atlassian.net/wiki/spaces/EDTW/pages/1661141027/Creating+Care+Plans)


## Known limitations
Login and security is currently not implemented in the demo projects. All authentication is hard coded and handleded automatically in the BFF projects. The Patient Web App is currently hard coded to use a specific patientId for all actions.




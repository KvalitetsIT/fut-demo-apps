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

## Flows implemented
_TODO_ 

## Known limitations
Login and security is currently not implemented in the demo projects. All authentication is hard coded and handleded automatically in the BFF projects. The Patient Web App is currently hard coded to use a specific patientId for all actions.




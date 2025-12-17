# Reflection: Patient Intake and Triage System Design

## Areas of Confidence
I feel most confident in the selection of MongoDB Atlas as the primary data store. Since patient intake forms and symptoms can vary significantly between cases, the document-based model provides the flexibility to store diverse JSON data without the need for rigid schema migrations. I am also confident in the use of Cloud Run. It provides a simple way to deploy the containerized Flask application while handling scaling automatically, which is ideal for a clinic that might see sudden spikes in patient volume.

## Areas of Uncertainty
The triage scoring algorithm represents my greatest area of uncertainty. While I have outlined a simple rule-based approach (keyword matching, severity weighting), I lack confidence in how well this would perform in a real clinical setting. Healthcare triage involves nuanced clinical judgment that a basic algorithm cannot fully capture. In practice, this component would require validation by clinical staff. I would want to consult with healthcare professionals to understand established triage protocols before implementing anything beyond a prototype. HIPAA compliance is another uncertain area for me. While the design incorporates encryption and access controls, actual HIPAA compliance involves administrative, physical, and technical safeguards that extend beyond architecture diagrams. Business Associate Agreements, security risk assessments, and breach notification procedures would all need to be addressed by someone with deeper compliance expertise.

## Alternative Architecture Considered
An alternative I considered was: using a serverless function-based architecture (e.g., GCP Cloud Functions) instead of the single, containerized Flask application running on Cloud Run. I decided against this because, while pure serverless functions are great for isolated, event-driven tasks (like processing a form submission or calculating a triage score), they are less suitable for hosting a complex, dynamic web application like the Staff and Clinician Dashboards required for queue management. Adopting a Cloud Function approach would force me to decompose the single, cohesive Flask application into numerous separate functions and require a dedicated static web hosting solution for the frontend. This increases developmental complexity and makes managing security and authorization across many decoupled endpoints more challenging than securing a single container environment. 

## Future Enhancements (With More Time and Resources)

If I had 4-8 additional weeks and unlimited cloud credits, I would prioritize the following enhancements:

**1. AI-Powered Triage Assistance**
I would integrate a machine learning service to improve triage accuracy. Using de-identified historical patient data, a classification model could learn patterns that correlate symptoms with actual triage outcomes. The model would provide a recommended triage level that staff could accept or override, with feedback loops to improve accuracy over time. This transforms the simple rule-based algorithm into a clinically-informed decision support tool.

**2. EHR Integration Layer**
Most clinics use Electronic Health Record systems (Epic, Cerner, etc.) that store patient history. Adding a FHIR-based API integration layer would allow the intake system to pull existing patient demographics (reducing data entry) and push completed visit summaries back to the EHR. This transforms the intake system from a standalone tool into an integrated component of the clinical workflow.

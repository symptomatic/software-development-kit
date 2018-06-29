## Build Pipelines  

When we discuss build pipelines with Symptomatic, there are two important pipelines to be aware of.  The first is the Meteor Build Pipeline.  Meteor.js is a technology developed by MIT alumni and the Open Source Community, which takes javascript files and prepares them for deployment to servers and clients.  It's basically a code compiler for Javascript.  

As you might imagine, a code compiler has many functions and features.  The important features we want to address right now are that Meteor has two package managers...  the Node Package Manager (NPM), which handles the basic 'building blocks' of javascript; and Atmosphere, which is a higher-level more abstracted package manager, which we use for workflow components.   These packages are pulled together into Clinical Meteor, where we add validation and verification testing (necessary for FDA regulation) and security audits (for HIPAA).  After pulling various packages into Clinical Meteor, we have a base build called 'Meteor on FHIR', where we add Fast Healthcare Interoperability Resources, and support connecting to EHR vendors and extracting Continuity of Care Documents.  

![Meteor Build Pipeline](https://raw.githubusercontent.com/symptomatic/software-development-kit/master/images/Meteor%20Build%20Pipeline%20-%20Page%201.png)  


The second pipeline we regularly deal with is our business pipeline, wherein we use the above technical pipeline, and apply it towards business use.  

![Client Engagement Build Pipeline](https://raw.githubusercontent.com/symptomatic/software-development-kit/master/images/ProfessionalServicesBuildPipeline.png)  

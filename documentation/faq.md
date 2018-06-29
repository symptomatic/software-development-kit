#### Q: Where can I find technical material and API specifications?  

Symptomatic Desktop is built on the Meteor on FHIR Community Server.  You’ll find extensive documentation in the Meteor Guide and API specification for Fast Healthcare Interoperability Resources.  Source code for the base build and FHIR packages are available on GitHub.  Each GiHub repository has an associated Readme.

[http://guide.meteor.com](http://guide.meteor.com)  
[http://github.com/clinical-meteor/meteor-on-fhir](http://github.com/clinical-meteor/meteor-on-fhir)  
[http://github.com/clinical-meteor/software-development-kit](http://github.com/clinical-meteor/software-development-kit)  
[http://github.com/symptomatic/software-development-kit](http://github.com/symptomatic/software-development-kit)

#### Q: What is the current feature set?  

So many to list!  At it’s most basic, Symptomatic Desktop allows you to load and edit a Continuity of Care Document that uses Fast Healthcare Interoperability Resources.  We include a longitudinal timeline and geospatial map, so you can visualize the contents of your health record.

Symptomatic Desktop is based on the Meteor on FHIR Community Server, which includes a FHIR interface engine and router and plugin architecture.  An audit log and privacy screen are provided for HIPAA compliance, and we keep everything under a quality control process using validation and verification tests, as per FDA requirements.  We provide everything within a responsive and reactive augmented reality interface that’s optimized for medical illustrations, and includes features as a complete user accounts system, push notifications, privacy screens, and more.

#### Q: What modules are available for sponsorship?  

In building Symptomatic, we created over 50 early prototypes.  Many of these prototypes eventually became the FHIR resource packages that are included by default, and allow us to render a Continuity of Care Document.  Others were simply experimental ideas that never went anywhere.  And others were advanced functionality that multiple teams have requested, but which have complicated aspects about them.  Some of our more popular modules that people like use include:

- Questionnaire Builder  
- Care Planner Builder  
- Clinical Trials Framework  
- Scheduling Calendar  
- Phylogenetic Trees & Cladograms  
- Graphs & Dashboards  
- Rules Engine  
- Conversational User Interface  
- DICOM Viewer  
- GraphQL Server  

#### Q:  How do you fetch charts?   

We fetch medical charts from Electronic Health Records using the Fast Healthcare Interoperability Resource protocol.  It’s a modern interoperability protocol based on web standards, as defined by Health Level Seven (HL7), the World Wide Web Consortium (W3C), and the American National Standards Institute (ANSI).

#### Q:  Is this being done by FHIR, other legacy HL7 protocols, or Epic proprietary interfaces?   

We strive to be 100% web standards based, and currently only support fetching data using FHIR.  We don’t support proprietary APIs or interfaces.  We have a licensable module available for outbound HL7 v2 interfaces for write access back to external legacy systems.  That being said, we also support a plugin architecture, so if you want to add a proprietary interface, you can probably add it within a plugin!

#### Q:  How is authentication/authorization to Epic handled at present?

Symptomatic uses the OAuth2 protocol to authenticate to Epic. Your application will be registered with App Orchard or the local Epic instance and provided a ClientID, which is then used during authentication.  If using Symptomatic as a caching layer for your Node app, a ‘Sign in with Epic MyChart’ button will need to be added to your site, which will launch a pop up dialog box with username/password for MyChart.  We intend to support OAuth proxy functionality via REST endpoints and redirects in the near future.  Unlike most other OAuth implementations, Symptomatic supports multi-token OAuth, meaning it can be configured as a client to many FHIR servers at the same time.  This allows Symptomatic users to store authentication credentials from multiple hospitals, clinics, and healthcare providers they interact with.

#### Q:  What is the caching layer?  

At its heart, Symptomatic is built on a FHIR router and interface engine.  It has the ability to fetch, receive, relay, and transmit Fast Healthcare Interoperability Resources, just like a network router does with regular internet traffic.  As it does this, you have the option to store or pool the data.  This function is called caching.  

A common scenario we encounter is a junior development team begins building a healthcare app at the request of a physician, and hit a wall when they try to fetch data from the EHR because their app wasn’t built from the ground up with interoperability in mind.  If the app happens to be build with Node.js, Symptomatic can provide the data routing and bridging piece.  As this happens, many clients prefer to persist and store the data for 30 or 90 days or more, so they don’t have to refetch data.  Caching requires HIPAA grade encrypted storage.  If the data is stored indefinitely, we refer to the Symptomatic instance as running in PHI Vault mode.   

#### Q:  How are caching policies defined?    

Caching policies are currently defined in plugins using javascript. We implement the caching policies using a scheduler module and a publication/subscription module.  This functionality is also used for data pipelining.

#### Q:  How are routing policies defined?   

Routing policies are currently defined in plugins using javascript. We implement the routing policies using collection hooks and observers, which then trigger an HTTP post call.

#### Q:  What assumptions of writability are being made to the Epic Chart?  

Currently, Symptomatic requires that any data written to Epic MyChart be routed through an HL7 v2 interface.  This requires additional license and implementation fees, as each Epic instance has a custom configuration.

#### Q:  Can you describe the build pipeline and tooling for the pipeline?  

Symptomatic is built with Meteor.js, a project originally written by MIT alumni, and which we consider to be the most advanced JavaScript/Node build pipeline available.  At it’s core, the build pipeline bundles packages into source code, and is the JavaScript equivalent of a compiler.  Of important note is that Meteor originally wrote its own package manager called Atmosphere, and has been migrating towards using the Node Package Manager (NPM).  After building a few dozen prototypes with Meteor with great success, we felt it warranted creating a release distro that was optimized for HIPAA compliance, FDA readiness, and EHR integration; which was subsequently named Clinical Meteor.  

Roughly speaking, the build pipeline can be characterized as the following:  we take NPM packages which contain JavaScript building blocks and assemble them into Atmosphere packages which contain workflow components.  We then take Atmosphere packages and put them under quality control and do security audits, wherein they are pulled into the Clinical Meteor release track.  We then take a large selection of those packages including all of the Argonaut FHIR packages, and assemble them into Meteor on FHIR and put that through additional validation testing.  We then compile the code to various platforms and devices.

#### Q:  Has Symptomatic been audited by a third party?    

Partially.  The bulk of third-party auditing is provided by way of the Meteor Development Group’s audit of the underlying platform, and by open-source peer review.  The simple fact of the matter, however, is that we’re the ones who are doing the auditing!  

We run the Clinical Meteor project, which actively audits open-source JavaScript libraries and pulls them into a unified framework that is verified and validated to be secure and interoperable.

#### Q:  Can you provide us copies of certification?   

Certifications such as ONC are pending at the current time.  We are actively in the auditing and submission process.  In the meantime please refer to our continuous integration server.

[https://circleci.com/gh/clinical-meteor/meteor-on-fhir/tree/master](https://circleci.com/gh/clinical-meteor/meteor-on-fhir/tree/master )  

#### Q:  How do you handle intellectual property?   

Symptomatic supports a plugin architecture for intellectual property.  Clients commonly keep validation and verification tests, business logic, proprietary datasets, and algorithms in their plugins.  The plugins can be public or private, and licensed however a client desires.  The FHIR resource packages are all MIT licensed, whereas the Meteor on Server Community Server is GPL licensed.

#### Q:  How do we protect our intellectual property?   

A typical enterprise integration will involve the use of the GPL interface engine, the MIT licensed FHIR packages relevant to the customer’s project, the proprietary Symptomatic OAuth plugin which the client licenses for use, and a proprietary private plugin that is custom built for the client.  

#### Q:  Were can we get a copy of the Material UI FHIR components?   

Search the clinical-meteor GitHub organization for ‘hl7-resource’ and you will find over 60 FHIR packages.  Most of the components are located in the /client or /client/react folders of the clinical-meteor/hl7-resource packages. 

[https://github.com/clinical-meteor?utf8=%E2%9C%93&q=hl7-resource&type=&language=](https://github.com/clinical-meteor?utf8=%E2%9C%93&q=hl7-resource&type=&language=)  

We are slowly refactoring them into pure functions, so we can extract them into the fhir-material-ui package (roughly inspired by the material-ui library).

[https://github.com/clinical-meteor/material-fhir-ui](https://github.com/clinical-meteor/material-fhir-ui)  

#### Q:  Why is Meteor on FHIR licensed differently than the FHIR packages?  

It basically has to do with the number of contributors and to what extent the package is a direct implementation of the FHIR standard.  Meteor on FHIR was originally released under the Artistic 2.0 License and represents an individual’s artistic work; while the FHIR packages represent the work of a much larger community of developers including a standards development organization (HL7).  

It’s important to note that the FHIR packages can be used outside of Meteor on FHIR.  A common pattern for back-end microservices is to use the FHIR resource packages without any user interface; in which case a client can truly do whatever they want according to the MIT license.  However, in such an implementation, you don’t get page routing, theming, notifications, workflow, visualizations, augmented reality, privacy screening, and the like.  Those are additional features Meteor on FHIR provides.  And if you use those features, we ask that you abide by the GPL v3 Affero license.

#### Q:  How do you handle wireframing during a client engagement?  

We do most of our wireframing using responsive Material UI React components.  We can lay down UI elements with React as fast as most people can use a wireframe editor; and it gets us that much closer to implementing a final solution.  We begin by doin an initial rendering pass on the device size of your choice (mobile or desktop).  After the wireframes are to a customer’s satisfaction on the preferred device, we then do a second render on the other size.  After getting sign off, we then wire up the components to the FHIR data layer. 

#### Q:  How do you handle code handoffs during a client engagement?  

We use GitHub for code development and intellectual property tracking and management.  Every client plugin has a readme with installation instructions on how to add it to the Meteor of FHIR Community Server.  Upon project completion or when the client requests, we will hand off the code by transferring ownership of the GitHub repository from our account to yours. 

#### Q:  Are you able to build mobile apps?  

Yes.   Symptomatic compiles to Android, iOS, MacOS, Linux, and Windows.  When building a plugin for Symptomatic, you can target the platform of your choice.  


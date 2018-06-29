# Symptomatic Software Development Kit  

Welcome to the Symptomatic SDK.  This repository is intended to help you develop software using Symptomatic, which is the brand name that the Meteor on FHIR Community Server is sold under.  


### Table of Contents  
- [Frequently Asked Questions](https://github.com/symptomatic/software-development-kit/blob/master/documentation/faq.md)  
- [Build Pipelines](https://github.com/symptomatic/software-development-kit/blob/master/documentation/build.pipelines.md)  
- [Creating a Plugin](https://github.com/symptomatic/software-development-kit/blob/master/documentation/creating.a.new.plugin.md)  
- [Plugin API](https://github.com/symptomatic/software-development-kit/blob/master/documentation/plugin.api.md)  
- [Setting Up a Development Environment](https://github.com/symptomatic/software-development-kit/blob/master/documentation/getting.started.md)  
- [Data Pipeline Overview](https://github.com/symptomatic/software-development-kit/blob/master/documentation/architecture.overview.md)  


### Community Source Code   
To begin developing, you will want to fetch the code from the following repositories.
- [Meteor on FHIR](https://github.com/clinical-meteor/meteor-on-fhir)  
- [Example Plugin](https://github.com/symptomatic/example-plugin)  

Alternatively, you can recursively fetch this repository, and pull in the submodules.
```sh
git clone --recursive http://github.com/symptomatic/software-development-kit

# you can also update to the latest versions of the submodules 
git submodule update
```

-----------------------------------------
#### Professional Services Build Pipeline  

Ensuring HIPAA, FDA, and EHR readiness is a complex task.  After consulting on dozens of healthcare websites and apps, we've developed the following production pipeline; wherein we currate javascript libraries into a technology stack that is ready to integrate with EHR platforms.   Your involvement using this SDK roughly corresponds with the blue lines in the diagram.

![Client Engagement Build Pipeline](https://raw.githubusercontent.com/symptomatic/software-development-kit/master/images/ProfessionalServicesBuildPipeline.png)  

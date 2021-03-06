# Symptomatic Software Development Kit  

Welcome to the Symptomatic SDK.  This repository is intended to help you develop plugins for Symptomatic, which is the brand name that the Meteor on FHIR Community Server is sold under.  


## Table of Contents  
- [Frequently Asked Questions](https://github.com/symptomatic/software-development-kit/blob/master/documentation/faq.md)  
- [Build Pipelines](https://github.com/symptomatic/software-development-kit/blob/master/documentation/build.pipelines.md)  
- [Creating a Plugin](https://github.com/symptomatic/software-development-kit/blob/master/documentation/creating.a.new.plugin.md)  
- [Plugin API](https://github.com/symptomatic/software-development-kit/blob/master/documentation/plugin.api.md)  
- [Data Pipeline Overview](https://github.com/symptomatic/software-development-kit/blob/master/documentation/architecture.overview.md)  


## Community Source Code   
To begin developing, you will want to fetch the code from the following repositories, and read the following documentation.
- [Setting Up a Meteor Development Environment](https://github.com/symptomatic/software-development-kit/blob/master/documentation/getting.started.md)  
- [Meteor on FHIR](https://github.com/clinical-meteor/meteor-on-fhir)  
- [Example Plugin](https://github.com/symptomatic/example-plugin)  
- [Meteor Guide](https://guide.meteor.com)  

Alternatively, you can recursively fetch this repository, and pull in the submodules.
```sh
git clone --recursive http://github.com/symptomatic/software-development-kit

# you can also update to the latest versions of the submodules 
git submodule update
```

## Professional Services Build Pipeline  

Ensuring HIPAA, FDA, and EHR readiness is a complex task.  After consulting on dozens of healthcare websites and apps, we've developed the following production pipeline; wherein we currate javascript libraries into a technology stack that is ready to integrate with EHR platforms.   Your involvement using this SDK roughly corresponds with the orange and blue lines in the diagram; depending on whether you're doing independent development or actively purchasing professional services from us.

![Client Engagement Build Pipeline](https://raw.githubusercontent.com/symptomatic/software-development-kit/master/images/ClientEngagementBuildPipeline.png)  

## Licensing   

Meteor on FHIR is a GPL licensed project that contains a plugin architecture and package management system.  It ships with a number of MIT licensed packages, particularly around the Fast Healthcare Interoperability Resource specification.  This plugin architecture allows you to build proprietary plugins for Symptomatic, where you can keep proprietary business data, algorithms, quality control scripts, and other business logic.  

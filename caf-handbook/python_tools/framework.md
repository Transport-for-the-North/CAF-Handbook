# Deployment Framework

This framework has been designed to help inform users of the current state of various CAF tools.
By creating a clear framework we are able to both set clear expectations for users of the tools
and provide pathways to development for each of the CAF modules.


# Release Stages
The below table summarises the different stages of CAF release within the framework.

```{list-table}
:header-rows: 1

* - CAF Release Status
  - Sharing
  - Description
  
* - Pre-Alpha
  - Private
  - Code is a work in progress, may be unstable and unreliable, and has little documentation. The main branch may not be functional.
  
* - Alpha
  - Private
  - Code is a work in progress, but may still be unstable. The main branch is functional and reliable. Some features (such as versioning) may begin to be incorporated.
  
* - Beta
  - Private - With exception allowed
  - Functionality is stable, a clear API is beginning to form. Functions, classes, and a simple user guide are in place. Many steps towards release will start to be incorporated.
  
* - Release
  - Public, Open License
  - Versioning, testing, and a clear API are now in place. All code is reviewed and technically documented. Integration into CAF is planned.
  
* - CAF Release
  - Public, Open License
  - Functionality is technically documented, expert reviewed (where applicable) and fully integrated into the CAF. Modules will be exstensively tested and easy to install and use.

```

# Classification and Progression
The below table details how the above stages are broken down into features for each type of release.


```{list-table}
:header-rows: 1

* - Feature
  - Pre-Alpha
  - Alpha
  - Beta
  - Release
  - CAF Release
  
* - Defined `requirements.txt`
  - Y
  - Y
  - Y
  - Y
  - Y
  
* - Functional Main
  - M
  - Y
  - Y
  - Y
  - Y
  
* - Stable API
  - M
  - M
  - Y
  - Y
  - Y
  
* - Software Versioning
  - N
  - M
  - Y
  - Y
  - Y
  
* - User Guide
  - N
  - M
  - Y
  - Y
  - Y
  
* - In-Code Documentation
  - N
  - M
  - M
  - Y
  - Y
  
* - Follows Coding Standards
  - N
  - M
  - N
  - Y
  - Y
  
* - Technical Documentation
  - N
  - M
  - M
  - Y
  - Y
  
* - Integration Tests
  - N
  - M
  - M
  - Y
  - Y
  
* - Run and Log Files
  - N
  - N
  - M
  - Y
  - Y
  
* - Unit Tests
  - N
  - N
  - M
  - M
  - Y
  
* - Expert Reviewed
  - N
  - N
  - N
  - M
  - Y
  
* - Integration into other CAF tools
  - N
  - N
  - N
  - M
  - Y
  
* - Deployed on PyPI / Conda-forge
  - N
  - N
  - N
  - M
  - Y
  
* - Published Code documentation
  - N
  - N
  - N
  - M
  - Y
```
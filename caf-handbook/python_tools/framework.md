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

<style>
span.yes_cell {
  color: green;
  font-weight: bold;
}
span.maybe_cell {
  color: orange;
  font-weight: bold;
}
span.no_cell {
  color: grey;
}
</style>

```{list-table}
:header-rows: 1

* - Feature
  - Pre-Alpha
  - Alpha
  - Beta
  - Release
  - CAF Release
  
* - Defined `requirements.txt`
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  
* - Functional Main
  - <span class="maybe_cell">M</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  
* - Stable API
  - <span class="maybe_cell">M</span>
  - <span class="maybe_cell">M</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  
* - Software Versioning
  - <span class="no_cell">N</span>
  - <span class="maybe_cell">M</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  
* - User Guide
  - <span class="no_cell">N</span>
  - <span class="maybe_cell">M</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  
* - In-Code Documentation
  - <span class="no_cell">N</span>
  - <span class="maybe_cell">M</span>
  - <span class="maybe_cell">M</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  
* - Follows Coding Standards
  - <span class="no_cell">N</span>
  - <span class="maybe_cell">M</span>
  - <span class="maybe_cell">M</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  
* - Technical Documentation
  - <span class="no_cell">N</span>
  - <span class="maybe_cell">M</span>
  - <span class="maybe_cell">M</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  
* - Integration Tests
  - <span class="no_cell">N</span>
  - <span class="maybe_cell">M</span>
  - <span class="maybe_cell">M</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  
* - Run and Log Files
  - <span class="no_cell">N</span>
  - <span class="no_cell">N</span>
  - <span class="maybe_cell">M</span>
  - <span class="yes_cell">Y</span>
  - <span class="yes_cell">Y</span>
  
* - Unit Tests
  - <span class="no_cell">N</span>
  - <span class="no_cell">N</span>
  - <span class="maybe_cell">M</span>
  - <span class="maybe_cell">M</span>
  - <span class="yes_cell">Y</span>
  
* - Expert Reviewed
  - <span class="no_cell">N</span>
  - <span class="no_cell">N</span>
  - <span class="no_cell">N</span>
  - <span class="maybe_cell">M</span>
  - <span class="yes_cell">Y</span>
  
* - Integration into other CAF tools
  - <span class="no_cell">N</span>
  - <span class="no_cell">N</span>
  - <span class="no_cell">N</span>
  - <span class="maybe_cell">M</span>
  - <span class="yes_cell">Y</span>
  
* - Deployed on PyPI / Conda-forge
  - <span class="no_cell">N</span>
  - <span class="no_cell">N</span>
  - <span class="no_cell">N</span>
  - <span class="maybe_cell">M</span>
  - <span class="yes_cell">Y</span>
  
* - Published Code documentation
  - <span class="no_cell">N</span>
  - <span class="no_cell">N</span>
  - <span class="no_cell">N</span>
  - <span class="maybe_cell">M</span>
  - <span class="yes_cell">Y</span>
```

<span class="yes_cell">Y</span>es,
<span class="maybe_cell">M</span>aybe,
<span class="no_cell">N</span>o

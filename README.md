# NCATS FHIR model 


## Creating the model
This repository contains an image of the FHIR R4 build with proposed ClinicalProfile additions, changes to the Group and
other models.  It is built from the https://github.com/NCATS-Tangerine/fhir-svn repository.

## Basic build instructions
```bash
> git clone https://github.com/NCATS-Tangerine/fhir-svn
> git clone https://github.com/NCATS-Tangering/fhir_publish
> mv fhir_publish fhir-svn/publish
> cd fhir_publish
> . publish.sh
```

The instructions above:
1) Clones the fhir source (fhir-svn) an existing object (fhir-publish) directory.
2) Renames the object directory as the target of the fhir source
3) Builds the source into the object

Assuming that the build is successful<sup>[1](#footnote1)</sup>, one can:
* Open `fhir-svn/publish/index.html` directly in a browser
* Change into the publish directory and commit/push it back to the origin

The contents of this repository are currently reflected on the [NCATS ClinicalProfile build](http://clinicalprofile.org) site.

This [Dockerfile](Dockerfile) can be used to deploy this on a target server.

## Notes
1) You can remove and regenerate the entire contents of this directory as long as you restore this file (README.md) and
the sample Dockerfile.  These can be restored via
   
   `git checkout -- README.md Dockerfile`
   
2) This is not a very efficient use of github.  One might consider adding `.zip` and some R2/R3 files to a .gitignore


<sup>**[1](#footnote1)** *You need to run `. publish.sh` at *least* twice in succession before you can be certain that
the entire build is a "take".  Note also that there are sometimes validation errors (which is the case with this build)
that occur late enough in the process as to not effect the outcome.*</sup>
# publish
Web image of ClinicalProfile FHIR model

## Installing on a cloud image
```bash
> mkdir fhir_publish
> cd fhir_publish
> curl https://raw.githubusercontent.com/ebmonfhir/publish/master/Docker/Dockerfile > Dockerfile
> docker build . -t model
> docker run  -d -p ${PORT}:80 --name model model
```

Where `${PORT}` is the port you want to expose

## Updating the cloud image
While you can restart the container, you can also:
```bash
> docker exec -it model /bin/bash
nnnnnnnn# cd fhir_publish
nnnnnnnn# git pull   (or vim file or whatever)

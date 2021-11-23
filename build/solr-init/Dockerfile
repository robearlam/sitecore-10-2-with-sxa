# escape=`
ARG BASE_IMAGE
ARG SXA_RESOURCES_IMAGE

FROM ${SXA_RESOURCES_IMAGE} AS sxa_resources
FROM $BASE_IMAGE as final

SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]

COPY --from=sxa_resources C:\module\solr\cores-sxa.json C:\data\cores-sxa.json
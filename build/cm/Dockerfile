# escape=`

ARG BASE_IMAGE
ARG SPE_RESOURCES_IMAGE
ARG SXA_RESOURCES_IMAGE

FROM ${SPE_RESOURCES_IMAGE} AS spe_resources
FROM ${SXA_RESOURCES_IMAGE} AS sxa_resources_image
FROM ${BASE_IMAGE}

SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]

WORKDIR C:\inetpub\wwwroot

# Copy SPE assets
COPY --from=spe_resources C:\module\cm\content .\

# Copy & setup SXA assets
COPY --from=sxa_resources_image C:\module\cm\content .\
COPY --from=sxa_resources_image \module\tools \module\tools
RUN C:\module\tools\Initialize-Content.ps1 -TargetPath .\; `
    Remove-Item -Path C:\module -Recurse -Force;
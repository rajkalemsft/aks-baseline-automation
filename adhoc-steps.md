
1. Prerequisites
    - Register Preview Features

            az feature register --namespace "Microsoft.ContainerService" -n "EnableOIDCIssuerPreview"

            az feature register --namespace "Microsoft.ContainerService" -n "AKS-AzureDefender"

    - Query Feature Availability


            az feature list -o table --query "[?name=='Microsoft.ContainerService/AKS-AzureDefender' || 
            name=='Microsoft.ContainerService/EnableOIDCIssuerPreview' || name=='Microsoft.ContainerService/EnableWorkloadIdentityPreview' || name=='Microsoft.ContainerService/EnableImageCleanerPreview'].{Name:name,State:properties.state}"


    - re-register the AKS resource provider

            az provider register --namespace Microsoft.ContainerService
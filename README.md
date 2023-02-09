# Apicurio Registry Security Demo

This example shows configuration to support a typical Apicurio Registry security design.

## Installation

### Provision Cert Manager

1. Install the cert-manager operator for all namespaces

2. Apply the certificate issuer resource instances

   `oc apply -f openshift-cert-manager/ -n openshift-cert-manager`

### Provision the Identity Provider

1. Create a namespace for Keycloak

   `oc new-project keycloak`

2. Install the Single Sign-On operator the `keycloak` namespace

3. Apply the Keycloak resource instances

   `oc apply -f keycloak/ -n keycloak`

### Provision the Kafka Cluster and Schema Registry

1. Create a namespace for Kafka
   
   `oc new-project kafka`

2. Install the AMQ Streams operator for all namespaces

3. Install the Service Registry Operator for all namespaces

4. Apply Kafka and ApicurioRegistry resource instances

   `oc apply -f kafka/ -n kafka`

## Demo

Use the postman collection in the `support` directory to test OAuth and RBAC scenarios.

TODO: Describe scenarios in detail.
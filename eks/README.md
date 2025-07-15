# Speaking Through Policies

Talk for the [Cloud Native Computing Foundation (CNCF)](https://cncf.io) Community Groups:
- Barcelona, Spain (March 2025) | 🔗 https://www.meetup.com/cloud-native-bcn/events/306257941/
- Málaga, Spain (July 2025) | 🔗 https://community.cncf.io/events/details/cncf-malaga-presents-cloud-native-talks-speaking-through-policies/

## Description

In a cloud-native world, platform engineers and application developers each have their own focus areas—security, scalability, reliability, and application logic. But how do they collaborate effectively without stepping on each other’s toes? Gateway Policies provide a structured way to define responsibilities and ensure alignment across teams. This talk explores how policies in Kubernetes—like networking, security, and traffic management—enable separation of concerns while fostering collaboration. We’ll dive into real-world scenarios where policies help teams work together seamlessly, ensuring consistency, compliance, and flexibility in modern cloud environments.

## The demo

The talk develops as a live demo play of the day-to-day interaction between 3 personas involved in the running of service applications on a Kubernetes cluster.

Continue to get acquainted with the personas and the tech. Click on each persona to see the corresponding steps and impersonate.

If you prefer, a version of this demo is available to run on [Kind](../README.md).

### Know the personas

#### Ana: App Developer

[![Ana](../images/ana-intro.png)](ana.md)

#### Chihiro: Cluster Operator

[![Chihiro](../images/chihiro-intro.png)](chihiro.md)

#### Ian: Infrastructure Provider

[![Ian](../images/ian-intro.png)](ian.md)

Ref.: https://gateway-api.sigs.k8s.io/concepts/roles-and-personas

### Tech

- [Kubernetes](https://kubernetes.io/)
- [Gateway API](https://gateway-api.sigs.k8s.io/)
- [Envoy Gateway](https://gateway.envoyproxy.io/)
- [Kuadrant](https://kuadrant.io/)
- [cert-manager](https://cert-manager.io/)
- [Amazon Route 53 Cloud DNS Service](https://aws.amazon.com/route53/)
- [AWS Load Balancer Controller](https://kubernetes-sigs.github.io/aws-load-balancer-controller/latest/)

### Requisites & Tweaks

To run the demo, you need the following tools installed on your system:

- [aws](https://aws.amazon.com/cli/)
- [kubectl](https://kubernetes.io/docs/reference/kubectl/introduction/)
- [Helm](https://helm.sh/)
- [curl](https://curl.se/)
- [jq](https://jqlang.org/)
- [yq](https://github.com/mikefarah/yq)

You will also need:

- A Kubernetes cluster | We are using [Amazon Elastic Kubernetes Service (EKS)](https://aws.amazon.com/eks)
- AWS Access key with permission to manage hosted managed zones in Route53

Export the credentials as the `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` shell variables.

The demo uses a public managed zone `demos.kuadrant.io`. Make sure to replace that across all commands with the FQDN associated to your hosted zone.

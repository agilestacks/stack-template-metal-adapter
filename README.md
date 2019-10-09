# Bare-metal Kubernetes Adapter Stack


This stack is for a bare-metal deployment which has no reliance on any cloud services.  In addition,  it leverages the outpost deployment mechanism, which runs automation-tasks on the destination cluster in order to install platform dependencies.

Like the hybrid stack, this uniquely directs api.${domain.name} to point to the NLB/ELB of the ingress tunnel.

This also relies on tls-host-adapter to automatically inject a `Ingress.spec.tls.host` array entry for every `Ingress.spec.rules.host` that exists.  This is so that cert-manager can automatically generate a cert for the ingress that is created in the cluster.

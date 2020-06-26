- RUN THE MIGRATION SCRIPT FIRST
- Upgrade jwt secret (first?). It must be 64 chars long.

- Upgrade cert-manager to latest (probably by completely uninstalling / reinstalling). Make sure all old CRDs are gone!!!!
- Upgrade the cluster issuer to the latest (`helm 2to3 convert cert-issuer -n cert-manager`)
- You might have to `kubectl delete cert-manager-webhook-ca -n cert-manager` to make this work

1. Install helm 3 and helm 2 at the same time (either can be run from whatever directory that they're downloaded to)
2. Install helm 2to3 into helm 3




5. `helm 2to3 move config --dry-run`, and make sure everything looks ok, then `helm 2to3 move config`
6. `helm 2to3 convert magda --dry-run` and make sure everything looks ok, then `helm 2to3 convert magda`
7. `helm 2to3 convert cert-manager` if necessary




Later: `helm 2to3 cleanup`
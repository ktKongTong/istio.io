---
---
The resulting mapping between revisions, tags, and namespaces is as shown below:

{{< image width="70%"
link="/docs/setup/upgrade/canary/tags.png"
caption="Two namespaces pointed to prod-stable and one pointed to prod-canary"
>}}

The cluster operator can view this mapping in addition to tagged namespaces through the `istioctl tag list` command:

{{< text bash >}}
$ istioctl tag list
TAG         REVISION NAMESPACES
prod-canary 1-10-0   ...
prod-stable 1-9-5    ...
{{< /text >}}

After the cluster operator is satisfied with the stability of the control plane tagged with `prod-canary`, namespaces labeled
`istio.io/rev=prod-stable` can be updated with one action by modifying the `prod-stable` revision tag to point to the newer
`1-10-0` revision.

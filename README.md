# external-dns on GKE with CloudFlare provider
Example how to run [external-dns](https://github.com/kubernetes-incubator/external-dns) on GKE with CloudFlare provider
# edit externaldns.yaml file
- edit `ENTER_CF_API_KEY`
- edit `ENTER_CF_EMAIL`
# create external-dns resources
`kubectl apply -f externaldns.yaml`
# check external-dns log
You might see a dns record being created

`time=“2018-02-25T21:53:08Z” level=info msg=“Changing record.” action=CREATE record=gke-test.marekbartik.com type=A zone=11d584e02796b157bbfd81fccff0f5fa`
# troubleshooting
- if you have any troubles creating the ClusterRole (granting extra privileges error), you might need [this fix](https://coreos.com/operators/prometheus/docs/latest/troubleshooting.html)

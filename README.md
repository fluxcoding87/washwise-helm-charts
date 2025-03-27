# Helm Charts for Kubernetes Deployment of application washwise
## Make sure you have a kubernetes cluster running and docker login with my personal dockerhub repo (contact me for access)
### Author Naman Pandey

###**Documented Process of how i created it**
1. Creation of helm chart
   > helm create <chart-name>
2. Clean up the chart template (delete unwanted files)
3. Copy existing kubernetes configs (deployments,services,configmaps) into the template
4. Test rendering of the template
   > helm template char-name /path/to/chart/dir
5. Package the chart
   > helm package <chart-dir>
6. Create a github repo to upload the chart and make a github page for /(root)
7. Git pull that repo
8. **Make sure that the packaged chart is into this newly created and pulled repo**
9. cd into the repo dir
10. Run the helm repo index command **Make sure you have you have hosted githubpages**
  > helm repo index . --url https://<your-username>.github.io/helm-charts
11. Add push and commit into your repo
```
git add .
git commit -m "Add packaged Helm chart and index"
git push origin main
```

## Now the helm chart is sucessfully uploaded to github repo and hosted into github pages

**Steps to add that repo to your env and install the helm chart**
1. Add the repo 
```
helm repo add washwise-helm-charts https://fluxcoding87.github.io/washwise-helm-charts/
```
2. Update repos
   ```
   helm repo update
   ```
3. Search the repo for a specific appversion and chart version
   ```
   helm search repo <repository_name>/<chart_name> --versions
   ```
4. I want to install a chart release using chart version 0.1.0 do this by
   ```
   helm install washwise-release washwise-helm-charts/washwise --version 0.1.0
   ```
### More Documentation Coming on the way ;)
   

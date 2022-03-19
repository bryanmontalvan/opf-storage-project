# Creating your own grafana dashboard and continue working on the Storage Dashboard

## How to create your own dashboard
Before we start here's an outline of steps you'll need to take in order to create and add your Grafana dashboard to our Grafana instance
1. Make sure you have access to our Grafana instance, [learn more](https://github.com/operate-first/apps/tree/master/cluster-scope/base/user.openshift.io/groups)
2. Create a dashboard to your liking
3. [Export the dashboard](https://grafana.com/docs/grafana/latest/dashboards/export-import/) via JSON File
4. Add your dashboard to the apps repository
5. Smile because you have now have a dashboard!

### Accessing the Grafana instance
Starting out you want to make sure you can access the Grafana instance, to gain access you'll have add yourself to one of these [groups](https://github.com/operate-first/apps/tree/master/cluster-scope/base/user.openshift.io/groups). You can do so by submitting a PR adding your GitHub username to the respective `group.yaml` file. 

(Note: Some groups have permissions that vary, if you are a co-op|intern you'll most likely be in the SRE group. For more questions reach out to members on the Slack)

Once you have access you want to go to our [Grafana instance page](https://grafana.operate-first.cloud/), there you are greeted with a login page. Click the *Sign in with OAuth* and now you'll be in an OpenShift login page. Log in with *operate-first*, for the first time you'll be redirected to a GitHub access page where you'll be asked to allow OpenShift to access to your GitHub account; Click yes and you'll be all set 


### Creating your first dashboard
Alright so you finally have access and you're on the Grafana instance landing page
<img src="https://user-images.githubusercontent.com/68972382/159065077-588e59c4-546e-439e-916e-0773d223f451.png" alt="dashboard image" width="800px"/>

Once you're on the landing page you should hover over the "+" button on the left side-bar. Click "Dashboard." And now you're in your newly created dashboard.

Here you can create various panels of various types of visualizations(graphs, pie-charts, tables, etc). Once you're done making your desired dashboard you should now save it. Click on the save icon and you will be prompted to "Save dashboard as..." write a meaning name and save the dashboard under a folder. Create save and now your dashboard has been saved to the Grafana instance.

### Backing up and exporting your dashboard
Now that you saved your dashboard to our Grafana instance you will now have to backup your dashboard locally, what does this mean? You see the Grafana instance/operator on OpenShift can be restarted (whether it be updates or a new dashboard has been added via a pull request). Whenever a restart happens all instance saved dashboards will be deleted (the dashboard you just created and saved). This means that any dashboard you save is ephemeral unless you add the dashboard to the [Apps repository](https://github.com/operate-first/apps).

Adding your dashboard can be done by following this guide from the [GitOps docs](https://www.operate-first.cloud/apps/content/grafana/add_grafana_dashboard.html). However, I will quickly go through the process it takes in adding a dashboard.
- Export the dashboard via json
  - Click the share icon on (left side of top bar), click on "Export" and then click "Save to file" So you will now have a json file of your dashboard

Here you would want to follow the guide linked above, in your `<dashboard-name>.yaml` file you can paste the json like such
```yaml
---
apiVersion: integreatly.org/v1alpha1
kind: GrafanaDashboard
metadata:
  labels:
    app: grafana
  name: namespace-storage-overview
spec:
  customFolderName: Cluster Management
  plugins:
    - name: grafana-piechart-panel
      version: 1.6.2
  json: |
    {
      "annotations": {
        "list": [
          {
  .............
```
After following the guide you should be set in having your dashboard pull request all set

### Conclusion
At this point consider yourself a Grafana master. You now know how to create, save, export, and deploy a dashboard to our grafana instance. Here is a list of links if you want to expand your understanding of Grafana
- [Grafana Docs](https://grafana.com/docs/)
- [Grafana Plugins](https://grafana.com/grafana/plugins/)
  

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

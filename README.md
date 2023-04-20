Helmfile:
This helps automate deployments to multiple environment.

So amongst numerous improvement i have brought to my team, one is the use of helmfile to automate our deployment to multiple environments.
In most cases i and my team will be tasked to deploy multiple application or even a single application to different environment say DEV/UAT/PROD.
In  many instances we will be required to deploy different replicas of the pod and other features that varies b/w the environments.

This project helped me solve the issues my team had with manually deplying workloads.

Create a working directory;
Install helm: brew install helm
You can use choco if you use windowns os 
Create a custom helmchart by running helm create <ChartName>

Once you crerate a helmchart, it comes with diff templates example.
1. Chart.yaml
2. values.yaml
3. deployment.yaml
4. template
5. helpers.tpl
6. ingress.yml
7. hpa.yml
8. service.yml and more ...

total of 3 directories and 10 files.

Click on chart.yml file and update the description to suit your project or release.

example Helm chart for springboot mongo application

click on values.yml and deployment.yml file created by helm and update what you have there to refflect your deployment or release goal.

Update you containerPort/image and also select your service type.

So amongst numerous improvement i have brought to my team, one is the use of helmfile to automate our deployment to multiple environments.
In most cases i and my team will be tasked to deploy multiple application or even a single application to different environment say DEV/UAT/PROD.
In  many instances we will be required to deploy different replicas of the pod and other features that varies b/w the environments.

Check the chart.yml on the version to reflect semantic v concept.

USING HELMFILE
The file in this repo shows the yaml file for helmchart and its syntax.

Commands to deploying your release:
run helm show chart <ChartName> ---> This will show you the informxn you have added to the chart.

To verify the chart
run helm template <version> <chartName>

To deploy your release
run helmfile sync --> This will deploy your release in an automated way

To deploy in an interactivly run
helmfile --debug --interactive apply --wait


Other useful commands

helm show chart <chartname>
helm template demochart
helm install <appname that you want to call the app> <chartname>
kubectl get po
helm upgrade ks8app demochart
kubectl describe po ks8app-demochart-7867bfd4fd-8m5
helm create demochart2
helmfile --interactive apply --wait (This will apply your release in an interactive manner or it will delete the release if you passed <installed: false> in your helmfile configuration)

helmfile sync (This will release all your definition in the helmfile configuration)
helmfile logs release-name
helmfile --debug --interactive apply --wait
Using the --debug flag provides more detailed logging output, which can be helpful in troubleshooting issues with helmfile. In this case, it allowed you to see what was happening during the deployment process and find a solution to the issue you were facing.



Helmfile:

#########
# Setup #
#########

# Install helmfile
https://helmfile.readthedocs.io/en/latest/
# Install helmfile diff plugin 
helm plugin install https://github.com/databus23/helm-diff
# Install helm git plugin
helm plugin install https://github.com/aslafy-z/helm-git --version 0.11.1




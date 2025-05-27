# guestbook
A simple guestbook application ('Final Project' in [Introduction to Containers w/ Docker, Kubernetes & OpenShift](https://www.coursera.org/learn/ibm-containers-docker-kubernetes-openshift) course, part of [IBM Full Stack Software Developer Professional Certificate](https://www.coursera.org/professional-certificates/ibm-full-stack-cloud-developer)).

<img width="930" alt="up-app" src="https://github.com/user-attachments/assets/5ab3f1f7-325e-4228-8284-4b205ae43910" />

Guestbook.

# What does the project do?
## Overview
I built and deployed a simple guestbook application, Guestbook, using Kubernetes Deployments and Pods. I then applied Horizontal Pod Scaling to Guestbook and performed Rolling Updates and Rollbacks.

## Review Criteria
1. Update the Dockerfile.
2. Ensure that the guestbook image is pushed to IBM Cloud Container Registry (CR) correctly.
3. Implement version 1 of the Index page of the deployed Guestbook.
4. Create a Horizontal Pod Autoscaler (HPA).
5. Ensure that the replicas in the HPA are scaled correctly.
6. Use Docker build and push commmands to update Guestbook.
7. Configure the deployment for autoscaling.
8. Implement version 2 of the index page of the deployed Guestbook after rollout of the deployment.
9. Examine the revision history for the deployment after rollout of the deployment. (2 points)
10. Update the deployment after Rollback of the update.

# Why is the project useful?
The project and [the course's Hands-on Labs](https://gist.github.com/nathandeflavis/0786fcf5bcc9feeab33ec3bca5463b81) are opportunities to put my Docker, Kubernetes and OpenShift skills into practice.

# How can users can get started with the project?
You can run the application in [an IBM Skills Network lab environment](https://skills.network).

## Steps
### Verify environment and command-line tools
1. If a terminal is not already open, open a terminal window by using the menu in the editor: `Terminal > New Terminal`.
2. If you're not already on the `/home/project` folder, change to it: `cd /home/project`
3. Clone this repository: `[ ! -d 'guestbook' ] && git clone https://github.com/nathandeflavis/guestbook.git`
4. Change to the `guestbook/v1/guestbook` directory: `cd guestbook/v1/guestbook`

 ### Build the guestbook app
1. Export your namespace as an environment variable: `export MY_NAMESPACE=sn-labs-$USERNAME`
2. Build the guestbook app: `docker build . -t us.icr.io/$MY_NAMESPACE/guestbook:v1`
3. Push the image to IBM Cloud Container Registry: `docker push us.icr.io/$MY_NAMESPACE/guestbook:v1`
4. Verify that the image was pushed successfully: `ibmcloud cr images`
5. In the `deployment.yml` file in the `v1/guestbook` directory, change the `template: spec: containers: -image` to use the format: `us.icr.io/<your sn labs namespace>/guestbook:v1`
6. Apply the deployment: `kubectl apply -f deployment.yml`
7. In a new terminal, view the application: `kubectl port-forward deployment.apps/guestbook 3000:3000`
8. Click on the Skills Network button on the right.
9. In the **'Skills Network Toolbox'**, click **Other**, then **Launch Application**.
10. For the Application Port, enter: `3000`
11. Press the return key.

# Where can users can get help with the project?
Users can contact the project's maintainers and contributors for help.

# Who maintains and contributes to the project?
@nathandeflavis

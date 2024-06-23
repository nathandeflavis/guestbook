# guestbook
A simple guestbook application (Final Project in [Introduction to Containers w/ Docker, Kubernetes & OpenShift](https://www.coursera.org/learn/ibm-containers-docker-kubernetes-openshift) course, part of [IBM Full Stack Software Developer Professional Certificate](https://www.coursera.org/professional-certificates/ibm-full-stack-cloud-developer)).

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

## Screenshots
<img width="1023" alt="app" src="https://github.com/nathandeflavis/guestbook/assets/92447278/685f886d-640f-44ba-838f-c7e79e5e9243">
<br />
<sub>Version 1 of the app.</sub>
<br />
<img width="1552" alt="crimages" src="https://github.com/nathandeflavis/guestbook/assets/92447278/05744c76-c6ef-4892-9966-493f28e302e4">
<br />
<sub>CR images.</sub>
<br />
<img width="782" alt="deployment" src="https://github.com/nathandeflavis/guestbook/assets/92447278/fe1d4b90-6fda-41c9-9e05-e0eb0ab487c9">
<br />
<sub>Deployment.</sub>
<br />
<img width="635" alt="hpa" src="https://github.com/nathandeflavis/guestbook/assets/92447278/415c6450-7a40-4790-8678-c466a231ad27">
<br />
<sub>HPA.</sub>
<br />
<img width="628" alt="hpa2" src="https://github.com/nathandeflavis/guestbook/assets/92447278/cb99e855-d207-4f34-b483-362cebffc83c">
<br />
<sub>Updated HPA.</sub>
<br />
<img width="985" alt="rev" src="https://github.com/nathandeflavis/guestbook/assets/92447278/38ebf18d-fcfa-4e94-a617-11fd2bfa0105">
<br />
<sub>Revision #2.</sub>
<br />
<img width="658" alt="rs" src="https://github.com/nathandeflavis/guestbook/assets/92447278/e01ab326-d9fd-4d4b-9675-b1331a6fa0bf">
<br />
<sub>ReplicaSets.</sub>
<br />
<img width="1024" alt="up-app" src="https://github.com/nathandeflavis/guestbook/assets/92447278/1292ec69-a170-4d7a-a532-5e0a757f0fc3">
<br />
<sub>Version 2 of the app.</sub>
<br />
<img width="1028" alt="upguestbook" src="https://github.com/nathandeflavis/guestbook/assets/92447278/a4250b7b-4789-4371-9e8f-371c32364923">
<br />
<sub>Building a Docker image and pushing it to the CR.</sub>
<br />

# Why is the project useful?
The project and [the course's Hands-on Labs](https://gist.github.com/nathandeflavis/0786fcf5bcc9feeab33ec3bca5463b81) are opportunities to put my Docker, Kubernetes and OpenShift skills into practice.

# How can users can get started with the project?
You can run the application in [an IBM Skills Network lab environment](https://skills.network).

## Steps
### Verify environment and command-line tools
1. If a terminal is not already open, open a terminal window by using the menu in the editor: `Terminal > New Terminal`.
2. If you're not already on the `/home/project` folder, change to it: `cd /home/project`
3. Clone this repository: `[ ! -d 'guestbook' ] && git clone https://github.com/nathandeflavis/guestbook`
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
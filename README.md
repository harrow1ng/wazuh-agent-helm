# Wazuh Agent Helm Chart

Deploy the **Wazuh Agent** as a **DaemonSet** in Kubernetes using Helm.

---

## Repository

Add the Helm repository to your local Helm client:

```bash
helm repo add wazuh-agent https://harrow1ng.github.io/wazuh-agent-helm/
helm repo update
```
Installation
Install the chart with default values:

```bash
helm install wazuh-agent wazuh-agent/wazuh-agent \
  --set manager.host=your-managers-ip \
  --set image.tag=4.13.1
```
This will deploy a Wazuh Agent DaemonSet on all nodes in your cluster.

```bash
Values
Key	Type	Default	Description
namespace	string	wazuh-agent	Namespace where the DaemonSet is deployed
image.repository	string	wazuh/wazuh-agent	Wazuh Agent image repository
image.tag	string	4.13.1	Image tag/version
image.pullPolicy	string	IfNotPresent	Image pull policy
manager.host	string	your-managers-ip	Wazuh Manager hostname or IP
manager.port	int	1514	Wazuh Manager port
securityContext.runAsUser	int	0	User ID to run container
securityContext.privileged	bool	true	Whether to run container in privileged mode
nodeSelector	map	{}	Node selector labels
tolerations	list	[]	Pod tolerations
affinity	map	{}	Pod affinity rules
resources	map	{}	Resource requests/limits
```



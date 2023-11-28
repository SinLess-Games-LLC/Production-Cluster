## System requirements

📍 _k3s default behaviour is that all nodes are able to run workloads, including contol nodes. Worker nodes are therefore optional._

📍 _If you have 3 or more nodes it is strongly recommended to make 3 of them control nodes for a highly available control plane._

📍 _Ideally you will run the cluster on bare metal machines. If you intend to run your cluster on Proxmox VE, my thoughts and recommendations about that are documented [here](https://onedr0p.github.io/home-ops/notes/proxmox-considerations.html)._

| Role             | Cores    | Memory        | System Disk               |
|------------------|----------|---------------|---------------------------|
| Control          | 4 _(6*)_ | 8GB _(24GB*)_ | 100GB _(500GB*)_ SSD/NVMe |
| Worker           | 4 _(6*)_ | 8GB _(24GB*)_ | 100GB _(500GB*)_ SSD/NVMe |
| _\* recommended_ |

## Large Cluster

📍 _The following are the minimum CPU and memory requirements for nodes in a high-availability K3s server:_

📍 _vCPU count is calculated by multiplying number of processing threads per core with no of cores and occupied CPU sockets._
- Number of vCPUs = (No of Threads x No of Cores) x Physical CPU Number
- Number of vCPUs = (16 Cores x 32 Threads) x 1 CPU
- Number of vCPUs = = 512

📍 _As a personal recommendation I would recommend giving your nodes more resources to your nodes, for example if your cluster will be up to 10 nodes I would recommend doubling what is recommended 

| Deployment Size  | Nodes     | VCPUs      | Ram              |
|------------------|-----------|------------|------------------|
| Small            | Up to 10  | 2 _(4*)_   | 4 GB _(8GB*)_    |
| Medium           | Up to 100 | 4 _(8*)_   | 8 GB _(16GB*)_   |
| Large            | up to 250 | 8 _(16*)_  | 16 GB _(32GB*)_  |
| X-Large          | Up to 500 | 16 _(32*)_ | 32 GB _(64GB*)_  |
| XX-Large         | 500+      | 32 _(64*)_ | 64 GB _(128GB*)_ |
| _\* recommended_ |
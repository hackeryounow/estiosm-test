> [osm 相关文件下载](https://osm-download.etsi.org/ftp/)
>
> [osm官网](https://osm.etsi.org/)
>
> [osm 文档](https://osm.etsi.org/docs/user-guide/latest/)
>
> [代码](https://osm.etsi.org/gitlab/vnf-onboarding/osm-packages/-/tree/6adad0f6a9999b949d103b64ffa3699dd57cf078/Hackfest_Demos/OSM-MR11/Team-7-Shark)



![image-20230709202237527](https://pggo.oss-cn-beijing.aliyuncs.com/img/image-20230709202237527.png)

*来源：3GPP 23501*

![image-20230709202326256](https://pggo.oss-cn-beijing.aliyuncs.com/img/image-20230709202326256.png)

*关于切片管理的更多可查看3GPP 28530*



free5gc 

oai 

open5gs



```sh

osm vim-create --name k8s --user u --password p --tenant p --account_type dummy --auth_url http://192.168.59.99/dummy

osm k8scluster-add MY_CLUSTER --creds ~/.kube/config --vim k8s --k8s-nets '{k8s-net1: null}' --version "1.23" --description="Kubernetes Cluster"
```







juju helm

esti open mano (osm)

OAI核心网在github中有以及编写好的OAI bundles模块，`https://github.com/charmed-osm/oai-bundle.git`。虽然OAI bundles模块部署的网元只有OAI 核心网项目的最小支持，包括AMF, SMF, NRF, UPF，但可以满足对OSM实现核心网网元升级的实验需求

Step 1：下载oai-bundles 模块

![image-20220521192912139](https://pggo.oss-cn-beijing.aliyuncs.com/img/image-20220521192912139.png)

Step2：为OAI增加一个juju model ，切换model（为OAI创建一个独立的model）

![image-20220521223434250](https://pggo.oss-cn-beijing.aliyuncs.com/img/image-20220521223434250.png)

Step3：build Charms 即在为本地juju工具生成juju charm

`sudo snap install charmcraft --classic`

![image-20220522221732718](https://pggo.oss-cn-beijing.aliyuncs.com/img/image-20220522221732718.png)

Step4：等待UE及网元组件启动，检查网元状态

![image-20220523220239623](https://pggo.oss-cn-beijing.aliyuncs.com/img/image-20220523220239623.png)

Step5：检测amf接入的UE和gNB信息

![image-20220523220527765](https://pggo.oss-cn-beijing.aliyuncs.com/img/image-20220523220527765.png)

```
git clone https://osm.etsi.org/gitlab/vnf-onboarding/osm-packages.git

git switch -c 6adad0f6a9999b949d103b64ffa3699dd57cf078
Team-7-shark

wget https://osm.etsi.org/gitlab/vnf-onboarding/osm-packages/-/archive/6adad0f6a9999b949d103b64ffa3699dd57cf078/osm-packages-6adad0f6a9999b949d103b64ffa3699dd57cf078.tar.gz
```

![image-20221005223834327](https://pggo.oss-cn-beijing.aliyuncs.com/img/image-20221005223834327.png)

之后可以利用juju这个工具支持的action对网络功能进行升级等操作


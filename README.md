# roks-rhoai-terraform

A set of Terraform Scripts to provision an OpenShift cluster hosted on a VPC on IBM Cloud.

The cluster will be provisioned with two workers pools, tree 8x32 nodes to host OpenShift AI and tree GPU workers gx3.24x120.l40s to run your model.

TODO
* ADD a COS with HMAC


Hugging Face > Block Storage > Upload to COS

RClone from one COS to another COS


Arguments: 

--tensor-parallel-size
1
--enable-auto-tool-choice
--tool-call-parser
llama3_json
--chat-template
/mnt/models/tool_chat_template_llama3.1_json.jinja
--max-model-len
9000


> oc debug node/kube-d45l7jrf0pupmjh71hg0-rhoai-gpupool-000004a2
Starting pod/kube-d45l7jrf0pupmjh71hg0-rhoai-gpupool-000004a2-debug ...
To use host binaries, run `chroot /host`
Pod IP: 10.10.10.11
If you don't see a command prompt, try pressing enter.
sh-5.1# chroot /host
sh-5.1# lsblk
NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
nbd0    43:0    0     0B  0 disk
nbd1    43:32   0     0B  0 disk
nbd2    43:64   0     0B  0 disk
nbd3    43:96   0     0B  0 disk
nbd4    43:128  0     0B  0 disk
nbd5    43:160  0     0B  0 disk
nbd6    43:192  0     0B  0 disk
nbd7    43:224  0     0B  0 disk
vda    252:0    0   100G  0 disk
|-vda1 252:1    0     1M  0 part
|-vda2 252:2    0   127M  0 part
|-vda3 252:3    0   384M  0 part /boot
`-vda4 252:4    0  99.5G  0 part /var
                                 /run/nvidia/driver/host-etc/os-release
                                 /run/nvidia/driver/var/log
                                 /sysroot/ostree/deploy/rhcos/var
                                 /sysroot
                                 /usr
                                 /etc
                                 /
vdb    252:16   0 726.4G  0 disk
vdc    252:32   0   600G  0 disk /var/lib/kubelet/pods/a076aaec-3ae8-493d-a769-3de9404e7f3e/volume-subpaths/nginx-conf/pipelines-console-plugin/1
                                 /var/lib/kubelet/pods/0298563a-150c-471d-9af0-cc4a0601fab9/volume-subpaths/config-service-cabundle-volume/pac-webhook/1
                                 /var/lib/kubelet/pods/0298563a-150c-471d-9af0-cc4a0601fab9/volume-subpaths/config-trusted-cabundle-volume/pac-webhook/0
                                 /var/lib/kubelet/pods/82f4fb27-e93d-41d1-949d-61c5a78bc843/volume-subpaths/config-service-cabundle-volume/pac-watcher/1
                                 /var/lib/kubelet/pods/89bf4226-a04a-4ec1-9d00-ffd78072fef3/volume-subpaths/config-service-cabundle-volume/pac-controller/2
                                 /var/lib/kubelet/pods/89bf4226-a04a-4ec1-9d00-ffd78072fef3/volume-subpaths/config-trusted-cabundle-volume/pac-controller/1
                                 /var/lib/kubelet/pods/82f4fb27-e93d-41d1-949d-61c5a78bc843/volume-subpaths/config-trusted-cabundle-volume/pac-watcher/0
                                 /var/lib/kubelet/pods/2833a088-811c-4070-abb2-c66eb92f4c57/volume-subpaths/nvidia-mig-manager-entrypoint/nvidia-mig-manager/0
                                 /var/lib/kubelet/pods/0829d3a0-5f2f-4c4b-ab13-cab8c73ec8e5/volume-subpaths/nvidia-device-plugin-entrypoint/nvidia-device-plugin/0
                                 /var/lib/kubelet/pods/12e56524-b438-44ea-97ec-dea7692a9695/volume-subpaths/init-config/init-pod-nvidia-node-status-exporter/1
                                 /var/lib/kubelet/pods/1dc87dbc-6f20-4d63-ad01-8c4273338d64/volume-subpaths/nvidia-container-toolkit-entrypoint/nvidia-container-toolkit-ctr/0
                                 /var/lib/kubelet/pods/384c81db-c77c-42c0-9cd5-f300424315c1/volume-subpaths/config-service-cabundle-volume/watcher/2
                                 /var/lib/kubelet/pods/384c81db-c77c-42c0-9cd5-f300424315c1/volume-subpaths/config-trusted-cabundle-volume/watcher/1
                                 /var/lib/kubelet/pods/f6c22672-97f3-4418-9dab-5092cd88f3ad/volume-subpaths/config-service-cabundle-volume/api/3
                                 /var/lib/kubelet/pods/f6c22672-97f3-4418-9dab-5092cd88f3ad/volume-subpaths/config-trusted-cabundle-volume/api/2
                                 /var/lib/kubelet/pods/8ee31a23-53ad-41cb-b5cb-ffe116e4f265/volume-subpaths/config-service-cabundle-volume/retention-policy-agent/3

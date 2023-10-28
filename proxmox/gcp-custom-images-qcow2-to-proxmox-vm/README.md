# Step-1: Create custom image out of running Golden Image of Compute Engine in GCP

# Step-2: Custom images in the compute engine -->> Export it to GCS bucket in the format of qcow2

# Step-3: open proxmox shell debian and navigate to correct partition /dev/sda which have enough strorage
```
df -h
lsblk
wget <public-url of the qcow2 image in the gcs bucket>
```
# Step-4: 

# CMPE 283 - Assignment 1

Team Members: Satya Ashish Veda and Raviraj Wadnerkar



# Question 1

Satya Ashish Veda:
Created the GCP VM, uploaded the files provided in canvas to GCP, Checked the video tutorial provided to check how to make the c file and added  procbased, procbased2, procbased3 and executed the files to load the object to kernel.


Raviraj Wadnerkar:
Gone through the Linux module installation, Collaborated with team member Ashish and modified Entry and Exit controls in the c file


# Question 2 

Steps to complete the assignment 

1. Create a project in the GCP

2. Create a VM which has nested-virtualization feature, to create this VM we use GCP cloud shell and execute the following command
gcloud compute instances create cmpe283-vm-last \
    --enable-nested-virtualization \
    --zone=us-west1-a \
    --machine-type=n2-standard-8 \
    --network-interface="network-tier=PREMIUM,nic-type=VIRTIO_NET,stack-type=IPV4_ONLY,subnet=default" \
    --create-disk="auto-delete=yes,boot=yes,device-name=instance-1,image=projects/ubuntu-os-cloud/global/images/ubuntu-2004-focal-v20220204,mode=rw,size=200,type=pd-ssd" \
    --metadata=ssh-keys=ashishveda:"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDQcbG9rcqS4jSb+/6ZuVI6DVtIj3bCpoVTIdbw3Nd6KVzZ/uS6aOrh4tcZNjQMh5bQZc6yMUqjYz+C8jHSlImyLrkiEEav2t3Bxe38CWcD5GC7v0VLu9Ym10c3dAy596w2id01mVmM4/kYYKjeSIm0tTvaztGgoK7KaxqtepBxmUNGNAuNwWRwwZvk6xaJdA3Ju9TUo8G4Q4x7ZZNsb8blIWHpzpD8tcnIcewDEg4Tz/y/olL6XY5ii2GFxxxYGCFLlt6EFrunx98WKSc50zkzvT0qz/zCu0kNkiTPoS1Otig90rzaPAfcHUvzvgLemEeeNWDWs/RNdD3vmZyHMb2gjSt1/WCvtXtyUiEt59FO/qegA3DxsxfaKEH9qrXltDGlMd+5SVAGqWa2zc5iikbxiI4Kh2P7G6GukC4oILJOUnZzDWacpFcjQkSza5RrPt3wM/9KFnbhx9BhwmZo3tAyCE+1qouD+8tY2nF9BSf3cdUGWVP4rL/CZSBQ1oOHCjE= ashishveda@Ashishs-MacBook-Pro.local"



3. SSH into the VM from the UI or from command line

4. As the cmpe283-1.c and Makefile are provided for the assignment, We create those files from the VI editor and copied the content
5. Installed the required packages gcc and make from the command,
sudo apt install gcc make
6. Modified the cmpe283-1.c by adding procbased, procbased2, procbased3, Entry and Exit controls from the intel SDK
7. In the same directory, executed the "make" command, which generates .ko objects

8. Execute "sudo insmod cmpe283-1.ko” command to load the kernel object.

9. dmesg is used to view the output.
<img width="976" alt="Screenshot 2023-12-16 at 1 14 31 PM" src="https://github.com/AshishVeda/Virtualization-Assignment/assets/43827081/db0d7c8b-bb6b-4c0a-a28f-b26de3a634fe">



<img width="654" alt="Screenshot 2023-12-16 at 1 16 10 PM" src="https://github.com/AshishVeda/Virtualization-Assignment/assets/43827081/c12b5378-f55c-44c2-b0cb-cc217fa23290">

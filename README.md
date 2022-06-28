Este lab crea un cluster EKS con tres nodos de tipo t2.small en tres subredes publicas. Modificar la region y los nombres del cluster, las vpcs y clave para entrar en los nodos
ficheros:
vpc.tf crea las redes
eks-cluster crea el cluster
Una vez desplegado el cluster, ejecutar el siguiente comando para configurar kubectl
aws eks --region $(terraform output -raw region) update-kubeconfig --name $(terraform output -raw cluster_name)
NOTA: si falla este comando puede que tengamos una antigua config de kubectl en ese caso borrarla ( rm -rf ~/.kube )


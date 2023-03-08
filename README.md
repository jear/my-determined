# my-determined


    # helm install is here https://github.com/jear/determined-helm

```
conda activate determined.ai-py37

# I just need the cli
pip install -U determined-cli

# pip install -U determined


# In LYS lab
export DET_MASTER=mlde.gpu01.lysdemolab.fr

# Admin task
# det user login admin
# det -u admin user create pollen


det user login pollen
det user change-password pollen

det workspace create pollen-workspace
det project create pollen-workspace pollen-project
 
PROJECT_ID=`det project list pollen-workspace  --json | jq '.[0].id'`
echo $PROJECT_ID

# Some experiments 
cd examples/tutorials/mnist_pytorch/
 
det experiment create --project_id $PROJECT_ID  const.yaml .
 
det project list-experiments pollen-workspace pollen-project


# In LYS lab
export DET_MASTER=mlde.gpu02.lysdemolab.fr
PROJECT_ID=`det project list pollen-workspace  --json | jq '.[0].id'`
det experiment create --project_id $PROJECT_ID  const.yaml .


export DET_MASTER=mlde.gpu03.lysdemolab.fr
PROJECT_ID=`det project list pollen-workspace  --json | jq '.[0].id'`
det experiment create --project_id $PROJECT_ID  const.yaml .



```

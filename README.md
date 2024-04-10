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
# det -u admin user create user1

USER=jear
det user login $USER
det user change-password $USER

det workspace create $USER-workspace
det project create $USER-workspace $USER-project
 
PROJECT_ID=`det project list $USER-workspace  --json | jq '.[0].id'`
echo $PROJECT_ID

# Some experiments 
cd examples/tutorials/mnist_pytorch/
 
det experiment create --project_id $PROJECT_ID  const.yaml .
 
det project list-experiments $USER-workspace $USER-project


# In LYS lab
export DET_MASTER=mlde.gpu02.lysdemolab.fr
PROJECT_ID=`det project list $USER-workspace  --json | jq '.[0].id'`
det experiment create --project_id $PROJECT_ID  const.yaml .


export DET_MASTER=mlde.gpu03.lysdemolab.fr
PROJECT_ID=`det project list $USER-workspace  --json | jq '.[0].id'`
det experiment create --project_id $PROJECT_ID  const.yaml .
det experiment create --project_id $PROJECT_ID  distributed.yaml .
det experiment create --project_id $PROJECT_ID  adaptive.yaml .

```

# my-determined
```
conda activate determined.ai-py37
pip install -U determined
pip install -U determined-cli


#export DET_MASTER=mlde.gpu03.lysdemolab.fr

# In GL CoLo
export DET_MASTER=192.168.201.75


det user login admin
det -u admin user create jerome.armand@hpe.com


det user login jerome.armand@hpe.com
det workspace create jear-workspace
det project create jear-workspace jear-project
 
det project list jear-workspace
   ID | Name         | Description   |   # Experiments |   # Active Experiments
------+--------------+---------------+-----------------+------------------------
    2 | jear-project |               |               1 |                      1

# Some experiments in GL CoLo
git clone https://github.com/jear/gl-det-pytorch
cd gl-det-pytorch
git pull
cd tutorials/
cd mnist_pytorch/
 
det experiment create --project_id 2  const.yaml .
 
det project list-experiments jear-workspace jear-project
```

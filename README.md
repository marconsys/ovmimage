oVMimage
================
A set of ansible playbooks to work with images on oVirt clusters.<br/>

## Copyright
Copyright (c) 2020 Marco Napolitano<br/>
The author is Marco Napolitano, email: mannysys-AaaaT-outlook.com put at sign instead of -AaaaT-<br/>
The content of the repository is licensed under Apache License, available at: http://www.apache.org/licenses/LICENSE-2.0

## Disclaimer
THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## Description
This repository contains ansible playbooks to work with images on oVirt clusters.<br/>
The playbooks are implemented using oVirt ansible modules, that in turn use oVirt Python SDK.<br/>
Image download playbook, to be called from playbooks directory like this:<br/>
$ ansible-playbook -e cluster_name="NameOfCluster" -e image_id="idOfTheImageToDownload" -e image_path="localPathOfDownloadedImage" imagedownload.yml<br/>
Image description change playbook, to be called from playbooks directory like this:<br/>
$ ansible-playbook -e cluster_name="NameOfCluster" -e image_id="idOfTheImageForDescriptionChange" -e image_newdescription="newDescriptionOfTheImage" imagechangedescr.yml<br/>
Be sure to put right values in the variables. About "cluster_name", it is needed in order to call variable files:<br/>
group_vars/virtcluster_{{ cluster_name }}.yml - countaining parameters to connect to oVirt cluster<br/>
vault/secret_{{ cluster_name }}.yml - ansible vault containing password to connect to oVirt cluster<br/>
Password to read or modify ansible vault "vault/secret_example.yml" is "Example01".<br/>
According to ansible.cfg, the file containing vault password "~/.vault_ovm".<br/>
NB: playbooks tested on ansible 2.8, and ovirt-engine-sdk-python 4.4.1 installed with pip.<br/>

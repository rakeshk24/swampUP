Lab 6 - Advanced security


*Config JF CLI with the instance
* Create a policy called ‘high vulns without JAS’
* Create another policy called ‘high vulns with JAS’
* Create a watch called ‘watch without JAS’
    * Include policy - high vulns without JAS
* Create another watch called ‘watch with JAS’
    * Include policy - high vulns with JAS
* Go to Artifactory > Artifacts > select repo ‘docker-trial’ - we need to download the image from this repo
* Download the image exposures/latest from the repo docker-trial by running
    * docker login -u<username> <instance_name>
    * Enter password
    * docker pull <instance_name>/docker-trial/<imagename>:<tag_info>
* In the terminal, run
    * docker images - to find the path of the image just downloaded
    * jf docker scan <image_path:<tag_info> —watches watch without JAS
    * Notice the results
    * Now run jf docker scan <image_path:<tag_info> —watches watch with JAS
    * Notice how the number of results goes down
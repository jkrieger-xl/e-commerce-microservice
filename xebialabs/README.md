## e-commerce microservice application on AWS EKS 

The blueprint deploys an e-commerce microservice created using JHipster to AWS EKS.
XL deploy does the provisioning and deployment, while XL release orchestrates everything.

### Prerequisites.

1. If you do not have an XL Release and XL Deploy instance running, you can use this docker compose setup to spin one up. The setup also contains a pre-configured Jenkins Instance.
Please note that you need to obtain a trial licence or bring your own licence for XLR and XLD. Follow the below steps to use the docker compose files.
 
    1. Download the contents of https://github.com/xebialabs/e-commerce-microservice/tree/master/docker-compose/xebialabs into a folder, let's say `xl-platform`
    2. Copy licence for XLR into `xl-platform/xl-release/default-conf/` and licence for XLD into `xl-platform/xl-deploy/default-conf/`
    3. Run `docker-compose up --build` on the `xl-platform` folder.

2. Git clone [https://github.com/xebialabs/e-commerce-microservice/tree/blueprint-demo](https://github.com/xebialabs/e-commerce-microservice/tree/blueprint-demo)
3. Generate the blueprint with `xl blueprint -t aws/microservice-ecommerce`


To deploy this blueprint with XL Platform follow the below steps

1. Apply the generated yaml configurations

    ```
    xl apply -f xebialabs.yaml
    ```

2. Go to XL Release and look for the "jkrieger-e-commerce-ci-cd" template and start a new release from it.
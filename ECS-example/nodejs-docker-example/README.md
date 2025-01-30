## STEP 1: 

``` npm run build ```

- It will pick the typescript project and it creates a dist folder where our code is compiled.

## STEP 2:

``` npm start  ```

- The files that are on our disk will run on port number 8000. 

## STEP 3: 

``` docker build -t my-image . ```

- So, what this command will do it will build an image and We can use this image and run the container.


## STEP 4:

```  docker run -it -p 8000:8000 my-image```

- This command will start the port:8000, and within the container. Now, you can access your website on localhost:8000

## STEP 5:

- Go to Elastic container registry (ECR) and Create a repository on it, enter the name you want to set.
- Now, use push commands on the right top.
- Copy the commands and paste it on your IDE.

## STEP 6:

- Go to Elastic container services
- We will deploy the cotainer and create a service by creating a cluster (We can put multiple services withint the cluster)
- Create a cluster

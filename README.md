# Simple proxy to show content of a folder within a container


* Add a component to source code - folder `proxy` with `Dockerfile`.
![image](https://user-images.githubusercontent.com/702860/120597693-a847d700-c445-11eb-89fd-75ff3f94bb7f.png)
* In the `proxy`'s `Dockerfile` specify its port and target component URL with its port
![image](https://user-images.githubusercontent.com/702860/120597815-cf060d80-c445-11eb-9ea4-ea1b77aa8360.png)
* Add to the target component [following lines](https://github.com/satr/nginx-proxy-to-containers/blob/ac1c4391b82bbe13e0b0ecd6ee88903a6ae5e427/backend/Dockerfile#L11-L13), set extra port (where the target folder will be exposed) and put target component's main command
![image](https://user-images.githubusercontent.com/702860/120598034-112f4f00-c446-11eb-8578-187ca6b3824f.png)
* For Radix application - in the `radixconfig.yaml` add the `proxy` component and extra port, specified in the previous step
![image](https://user-images.githubusercontent.com/702860/120598309-68352400-c446-11eb-8c84-57362d57ca79.png)
* Opening the page with `proxy`'s port shows the target folder content (it is possible to navigate within it by subfolders and download files)

`docker-compose` can be also used on local PC. Run the command in the root of this repository source code
```
docker-compose up
```

# 4cast Exercise
When approaching open source software, even when costumizing it and configuring for personal uses it is recommended to make minimal changes.

I started with trying out the docker container and running it vanilla, to see how it operates. 

Then I messed with the docker file and injected the mapproxy.yaml file you have given me, so that on startup the container will already be configured with the correct mapproxy.yaml in the /mapproxy/config path. 

I ran the container with <mark>docker run --name mapproxy -d --rm -p 8080:8080 -p 80:80 exercise </mark>
after running the container, I have tried accesing port 80 and got the welcome page. I then tried to access port 8080 and got an error. using docker logs I encountered this error: invalid request block size: 21573 (max 4096)...skip.

To solve this error I change the usgwi.cong and increased the buffer size in it. Then I've built the image again and ran the container from the new image.

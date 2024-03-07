dive - image monitoring

https://github.com/wagoodman/dive

feature:
 - Show the contents of the Docker image layer by layer
 - Indicator of changes in each layer

install

alias dive="docker run -ti --rm  -v /var/run/docker.sock:/var/run/docker.sock wagoodman/dive"
dive <your-image-tag>

# for example
dive nginx:latest
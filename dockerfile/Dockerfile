# This is a multi-stage Dockerfile and requires >= Docker 17.05
# https://docs.docker.com/engine/userguide/eng-image/multistage-build/
FROM gobuffalo/buffalo:v0.9.4

# This is a multi-stage Dockerfile and requires >= Docker 17.05
# https://docs.docker.com/engine/userguide/eng-image/multistage-build/
RUN mkdir -p $GOPATH/src/github.com/dummy/bloggy
WORKDIR $GOPATH/src/github.com/dummy/bloggy

ADD package.json .
RUN npm install

# Add all files
ADD . .

# Generate a binary called app under bin folder
RUN buffalo build -o bin/app

# Run the app binary
CMD ./bin/app

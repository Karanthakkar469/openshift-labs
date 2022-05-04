# Use a container with Go pre-installed
FROM quay.io/practicalopenshift/hello-world

# Copy our source file into the container
COPY src/hello-world.go /go/hello-world.go

# Set the default environment variables
ENV MESSAGE "Hello from custom image by Karan."
ENV HOME /go

# OpenShift uses root group instead of root user
USER root

# Set permissions to the /go folder (for OpenShift)
RUN chgrp -R 0 /go && chmod -R g+rwX /go

# Just documentation.
# This container needs Docker or OpenShift to help with networking
EXPOSE 8080

# Command to run when container starts up
CMD go run hello-world.go

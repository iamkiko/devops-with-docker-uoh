# Use ubuntu:20.04 as the base image
FROM ubuntu:20.04

# Install curl
RUN apt-get update && apt-get install -y curl

# Copy the instructions.sh file from this location to /usr/src/app/ creating /usr/src/app/instructions.sh
COPY instructions.sh .

# Alternatively, if we skipped chmod earlier, we can add execution permissions during the build.
# RUN chmod +x hello.sh

# When running docker run the command will be ./hello.sh
ENTRYPOINT ./instructions.sh

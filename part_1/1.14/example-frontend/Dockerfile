# Prefer node over ubuntu as more lightweight
FROM node:16.13.0

# Set the working directory to /usr/src/app
WORKDIR /usr/src/app

# Copy the files required for dependencies to be installed
COPY . .

# ENV VAR FOR BE URL
ENV REACT_APP_BACKEND_URL http://localhost:8080
s
# Install dependencies and build the application
RUN npm install && npm run build && npm install -g serve

# Run the application
CMD ["npx", "serve", "-s", "-l", "8090", "build"]

EXPOSE 8090

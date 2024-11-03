# Use the official nginx image as the base image
FROM nginx:latest

# Run a command to display a message during the build (just for demo purposes)
RUN echo "Building the nginx container with custom index.html"

# Copy the custom index.html file to the nginx HTML folder
COPY index.html /usr/share/nginx/html/

WORKDIR /nginx

# Expose port 80
EXPOSE 80

# Use CMD to start nginx in the foreground
CMD ["nginx", "-g", "daemon off;"]
# Use the official Nginx image as the base image
FROM nginx:latest

# Remove the default Nginx configuration file
RUN rm /etc/nginx/nginx.conf

# Copy the custom Nginx configuration file to the container
COPY nginx.conf /etc/nginx/nginx.conf

# Expose the port that Nginx will listen on
EXPOSE 80

# Start Nginx when the container starts
CMD ["nginx", "-g", "daemon off;"]

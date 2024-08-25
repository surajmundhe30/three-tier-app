# FROM nginx:alpine
# COPY index.html /usr/share/nginx/html/index.html

# Use the official Nginx image
FROM nginx:alpine

# Copy the frontend files to the Nginx HTML directory
COPY . /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]

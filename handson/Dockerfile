# FROM alpine
# ADD log-event.sh /
# CMD ["/log-event.sh", "CMD image created"]


FROM nginx
# Expose port 80 to allow outside access
EXPOSE 80
# Start NGINX when the container launches
CMD ["nginx", "-g", "daemon off;"]

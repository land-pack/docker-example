# Use an official oeasy/xface runtime as a parent image
FROM oeasy/xface:v3

# Set the working directory to /app
WORKDIR /root

# Copy the current directory contents into the container at /app
ADD test.conf /etc/supervisor/conf.d/
ADD test /root/test


# Install any needed packages specified in requirements.txt


# Make port 80 available to the world outside this container
EXPOSE 5058


# Run app.py when the container launches
ENTRYPOINT ["supervisord", "-n", "-c", "/etc/supervisor/supervisord.conf"]
# ENTRYPOINT ["/usr/bin/supervisord"]
# ENTRYPOINT ["/bin/bash"]
#ENTRYPOINT ["/usr/bin/tail", "-f", "/dev/null"]
# CMD /bin/bash
# CMD supervisord

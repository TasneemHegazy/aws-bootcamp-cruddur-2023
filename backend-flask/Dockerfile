# First stage: build the application and install dependencies
FROM python:3.10-slim-buster AS build

WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip3 install --user --no-cache-dir -r requirements.txt

COPY . .

# Second stage: create a production image with a smaller base image
FROM python:3.10-slim-buster

# Set the working directory
WORKDIR /app

# Copy the application and dependencies from the previous stage
COPY --from=build --chown=root:root /root/.local /root/.local
COPY --from=build --chown=root:root /app /app

# Set environment variables
ENV PATH=/root/.local/bin:$PATH
ENV FLASK_ENV=production
ENV PORT=4567

# Expose the port
EXPOSE $PORT

# Switch to a non-root user
USER nobody

# Set the entrypoint
CMD ["./start.sh"]
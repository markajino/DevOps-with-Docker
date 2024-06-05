FROM ubuntu

EXPOSE 5000

WORKDIR /usr/src/app

# Install curl and Node.js
RUN apt-get update && \
    apt-get install -y curl && \
    curl -sL https://deb.nodesource.com/setup_16.x | bash && \
    apt-get install -y nodejs

# Copy project files
COPY . .

# Install dependencies and build project
RUN npm install && \
    npm run build && \
    npm install -g serve

# Start the application with serve
CMD ["serve", "-s", "-l", "5000", "build"]

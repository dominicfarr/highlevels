# Base image from node
FROM node:alpine

# Change Container's working direction
WORKDIR /app

# Copy package.json into container
COPY package.json .

# Run the npm to install packages based on package.json
RUN npm install

# Copy all other files into container
COPY . .

# Last command in file is the execution command
CMD ["node", "index.js"]
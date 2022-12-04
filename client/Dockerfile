FROM node:10.19.0-alpine

# Define working directory
WORKDIR /src/client

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy rest of the app to the working directory
COPY . .

# Expose port 3000
EXPOSE 3000

# Define entry point
CMD ["npm", "start"]
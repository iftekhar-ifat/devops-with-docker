FROM ubuntu:24.04
RUN apt-get update && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_16.x | bash
RUN apt-get install -y nodejs
RUN npm install -g serve

WORKDIR /usr/src/app
COPY package.json package-lock.json ./
RUN npm install
COPY . .
RUN npm run build

EXPOSE 5001
CMD ["serve", "-s", "-l", "5001", "build"]

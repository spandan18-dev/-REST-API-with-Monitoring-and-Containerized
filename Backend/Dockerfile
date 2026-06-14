FROM node:18 AS Builder
WORKDIR /Build
COPY package*.json /Build/
RUN npm install
COPY . /Build/

FROM node:18 
WORKDIR /app
COPY --from=Builder /Build /app/
ENV PORT=8000
ENV MONGODB_URL=mongodb://mongo:27017/project_cv1
ENV JWT_KEY=shdgsdfbdvno
EXPOSE 8000
CMD ["node", "app.js"]
FROM node:20.10.0 AS BUID_IMAGE_FRONT
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . ./
RUN npm run build
EXPOSE 5173

FROM node:22-alpine
WORKDIR /app
COPY --from=BUID_IMAGE_FRONT /app ./
# COPY --from=BUID_IMAGE_FRONT /app/node_modules ./node_modules
CMD npm run host
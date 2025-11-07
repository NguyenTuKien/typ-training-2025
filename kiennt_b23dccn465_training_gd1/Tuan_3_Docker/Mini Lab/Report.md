```dockerfile
FROM maven:3.9.6-eclipse-temurin-21 AS build
WORKDIR /app
COPY pom.xml .
COPY src ./src
RUN mvn clean package -DskipTests

FROM eclipse-temurin:21-jre-alpine
WORKDIR /app
ENV TZ=Asia/HoChiMinh
COPY --from=build /app/target/*.jar ./app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
```
```shell
ngtukien@NgTuKien:~/Documents/Mini Lab/Backend$ docker build -t minilab .
[+] Building 74.8s (16/16) FINISHED                                                                                                                                         docker:default
=> [internal] load build definition from Dockerfile                                                                                                                                  0.0s
=> => transferring dockerfile: 339B                                                                                                                                                  0.0s
=> [internal] load metadata for docker.io/library/eclipse-temurin:21-jre-alpine                                                                                                      2.0s
=> [internal] load metadata for docker.io/library/maven:3.9.6-eclipse-temurin-21                                                                                                     2.1s
=> [auth] library/eclipse-temurin:pull token for registry-1.docker.io                                                                                                                0.0s
=> [auth] library/maven:pull token for registry-1.docker.io                                                                                                                          0.0s
=> [internal] load .dockerignore                                                                                                                                                     0.0s
=> => transferring context: 2B                                                                                                                                                       0.0s
=> [build 1/5] FROM docker.io/library/maven:3.9.6-eclipse-temurin-21@sha256:8d63d4c1902cb12d9e79a70671b18ebe26358cb592561af33ca1808f00d935cb                                         0.0s
=> [stage-1 1/3] FROM docker.io/library/eclipse-temurin:21-jre-alpine@sha256:990397e0495ac088ab6ee3d949a2e97b715a134d8b96c561c5d130b3786a489d                                        0.0s
=> [internal] load build context                                                                                                                                                     0.0s
=> => transferring context: 17.14kB                                                                                                                                                  0.0s
=> CACHED [build 2/5] WORKDIR /app                                                                                                                                                   0.0s
=> CACHED [build 3/5] COPY pom.xml .                                                                                                                                                 0.0s
=> [build 4/5] COPY src ./src                                                                                                                                                        0.0s
=> [build 5/5] RUN mvn clean package -DskipTests                                                                                                                                    72.2s
=> CACHED [stage-1 2/3] WORKDIR /app                                                                                                                                                 0.0s
=> [stage-1 3/3] COPY --from=build /app/target/*.jar ./app.jar                                                                                                                       0.1s
=> exporting to image                                                                                                                                                                0.1s
=> => exporting layers                                                                                                                                                               0.1s
=> => writing image sha256:c1065c2eec785c884165d381b39f8ae28cc6ccd46a927614810df6bdd4c55ce0                                                                                          0.0s
=> => naming to docker.io/library/minilab
```
```dockerfile
# Dùng Node 20 (alpine = nhẹ)
FROM node:20-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 5173

# Lệnh chạy server phát triển
CMD ["npm", "run", "dev"]

```
```shell
ngtukien@NgTuKien:~/Documents/Mini Lab/Frontend$ docker build -t frontend . --no-cache
[+] Building 82.1s (11/11) FINISHED                                                                                                                                         docker:default
 => [internal] load build definition from Dockerfile                                                                                                                                  0.0s
 => => transferring dockerfile: 233B                                                                                                                                                  0.0s
 => [internal] load metadata for docker.io/library/node:20-alpine                                                                                                                     4.3s
 => [auth] library/node:pull token for registry-1.docker.io                                                                                                                           0.0s
 => [internal] load .dockerignore                                                                                                                                                     0.0s
 => => transferring context: 182B                                                                                                                                                     0.0s
 => [1/5] FROM docker.io/library/node:20-alpine@sha256:6178e78b972f79c335df281f4b7674a2d85071aae2af020ffa39f0a770265435                                                               4.2s
 => => resolve docker.io/library/node:20-alpine@sha256:6178e78b972f79c335df281f4b7674a2d85071aae2af020ffa39f0a770265435                                                               0.0s
 => => sha256:be8d32d651b3e0c9c2b28fdc1d3888408125d703232013cff955344d052027e5 1.72kB / 1.72kB                                                                                        0.0s
 => => sha256:2b56f2779663b9e1a77bdb5235dc31f1a81e534ccab1c1b35c716a8db79eeab9 6.42kB / 6.42kB                                                                                        0.0s
 => => sha256:60e45a9660cfaebbbac9bba98180aa28b3966b7f2462d132c46f51a1f5b25a64 42.75MB / 42.75MB                                                                                      3.6s
 => => sha256:e74e4ed823e9560b3fe51c0cab47dbfdfc4b12453604319408ec58708fb9e720 1.26MB / 1.26MB                                                                                        2.3s 
 => => sha256:da04d522c98fe12816b2bcddf8413fca73645f8fa60f287c672f58bcc7f0fa38 444B / 444B                                                                                            1.3s 
 => => sha256:6178e78b972f79c335df281f4b7674a2d85071aae2af020ffa39f0a770265435 7.67kB / 7.67kB                                                                                        0.0s 
 => => extracting sha256:60e45a9660cfaebbbac9bba98180aa28b3966b7f2462d132c46f51a1f5b25a64                                                                                             0.5s 
 => => extracting sha256:e74e4ed823e9560b3fe51c0cab47dbfdfc4b12453604319408ec58708fb9e720                                                                                             0.0s 
 => => extracting sha256:da04d522c98fe12816b2bcddf8413fca73645f8fa60f287c672f58bcc7f0fa38                                                                                             0.0s 
 => [internal] load build context                                                                                                                                                     0.0s 
 => => transferring context: 9.75kB                                                                                                                                                   0.0s 
 => [2/5] WORKDIR /app                                                                                                                                                                0.1s 
 => [3/5] COPY package*.json ./                                                                                                                                                       0.0s 
 => [4/5] RUN npm install                                                                                                                                                            73.3s 
 => [5/5] COPY . .                                                                                                                                                                    0.0s 
 => exporting to image                                                                                                                                                                0.0s 
 => => exporting layers                                                                                                                                                               0.0s 
 => => writing image sha256:aca09be5ae79c9e0f89f6cc5583703eaf81f2006972e87abe43e5ae7c7b9881b                                                                                          0.0s 
 => => naming to docker.io/library/frontend 
 ```

# Jenkins Docker Lifecycle Commands

## 1️⃣ Pull Jenkins Image

``` bash
docker pull jenkins/jenkins:lts
```

------------------------------------------------------------------------

## 2️⃣ Create Docker Volume (Recommended for Data Persistence)

``` bash
docker volume create jenkins_home
```

------------------------------------------------------------------------

## 3️⃣ Run Jenkins Container

``` bash
docker run -d   -p 8080:8080   -p 50000:50000   -v jenkins_home:/var/jenkins_home   --name jenkins   jenkins/jenkins:lts
```

------------------------------------------------------------------------

## 4️⃣ Check Running Containers

``` bash
docker ps
```

------------------------------------------------------------------------

## 5️⃣ Get Initial Admin Password

``` bash
docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```

------------------------------------------------------------------------

## 6️⃣ Stop Jenkins Container (Safe - Keeps Data)

``` bash
docker stop jenkins
```

------------------------------------------------------------------------

## 7️⃣ Start Jenkins Again

``` bash
docker start jenkins
```

------------------------------------------------------------------------

## 8️⃣ Restart Jenkins

``` bash
docker restart jenkins
```

------------------------------------------------------------------------

## 9️⃣ Remove Jenkins Container (Keeps Data if Volume Exists)

``` bash
docker rm jenkins
```

------------------------------------------------------------------------

## 🔟 Remove Jenkins Container Forcefully

``` bash
docker rm -f jenkins
```

------------------------------------------------------------------------

## 1️⃣1️⃣ Remove Volume (⚠️ Deletes All Jenkins Data)

``` bash
docker volume rm jenkins_home
```

------------------------------------------------------------------------

## 1️⃣2️⃣ Remove Jenkins Image

``` bash
docker rmi jenkins/jenkins:lts
```

------------------------------------------------------------------------

# 🔐 Important Notes

-   `docker stop` → Safe (Data remains)
-   `docker rm` → Removes container only
-   `docker volume rm` → Permanently deletes Jenkins data
-   Always use volumes for production setups

------------------------------------------------------------------------

🚀 Recommended Safe Workflow: 1. Stop → `docker stop jenkins` 2. Start →
`docker start jenkins` 3. Remove (if needed) → `docker rm jenkins` 4.
Never remove volume unless you want to reset everything

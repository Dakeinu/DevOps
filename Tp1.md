## TP 1 ##

3. Exécuter un serveur web (apache, nginx, …) dans un conteneur docker
    a) root@debian:/home/dakeinu# docker run it --rm -d -p 8080:80 --name some-nginx -v /some/content:/usr/share/nginx/html -d nginx
    
    Unable to find image 'nginx:latest' locally
    latest: Pulling from library/nginx
    b380bbd43752: Pull complete 
    fca7e12d1754: Pull complete 
    745ab57616cb: Pull complete 
    a4723e260b6f: Pull complete 
    1c84ebdff681: Pull complete 
    858292fd2e56: Pull complete 
    Digest: sha256:644a70516a26004c97d0d85c7fe1d0c3a67ea8ab7ddf4aff193d9f301670cf36
    Status: Downloaded newer image for nginx:latest
    584daf1962fc7b10483c30d1821da61965f885be2f4c6ee37c3950245405cf2b

    b) root@debian:/home/dakeinu# docker images

    REPOSITORY    TAG       IMAGE ID       CREATED       SIZE
    nginx         latest    87a94228f133   6 days ago    133MB
    hello-world   latest    feb5d9fea6a5   3 weeks ago   13.3kB

    c) root@debian:/home/dakeinu/Documents/DevOps# touch index.html

    d) docker run -it --rm -d -p 8080:80 --name web -v /home/dakeinu/Documents/DevOps:/usr/share/nginx/html nginx

    e) docker cp Documents/DevOps some-nginx:/usr/share/nginx/html/

4. Builder ue image
    a) docker build -t my-docker-file .

    b) docker run -d -p 8080:8080 my-docker-file

    c) Le résultat final est le même qu'avec la version précédente cependant celle ci est plus rapide d'execution.
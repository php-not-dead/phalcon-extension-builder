### How to build phalcon.so extension

1. Edit `Dockerfile` by setting PHP and Phalcon versions
2. `docker build -t phalcon_ext_builder .`
3. `docker run -d --name phalcon_ext_builder phalcon_ext_builder`
4. `docker exec -it phalcon_ext_builder bash`
5. `ls /usr/local/lib/php/extensions` -> `no-debug-non-zts-20190902` is the dir you need (change "20190902" with another value if it differs)
6. `exit`
7. `docker cp phalcon_ext_builder:/usr/local/lib/php/extensions/no-debug-non-zts-20190902/phalcon.so ./phalcon.so`
8. `docker stop phalcon_ext_builder && docker rm phalcon_ext_builder`
9. `docker image rm phalcon_ext_builder`

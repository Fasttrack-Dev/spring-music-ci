# spring-music-ci

## deploy the config
```sh
bash$ fly set-pipeline -t ft -p beanstalk-speedway -c beanstalk/spring-example-beanstalk.yml
```

## develop a pipeline local
you can put everything in one file but if you split off you facing the problem how to test this before you commit.
Use the option `execute` and ann the input from local

```sh
bash$ fly -t ft e -c beanstalk/tasks/test.yml -i ci-tasks=. -i spring-boot-music=../spring-music
```

## ci image from dockerhub  

we use the baseic gradle image in our pipeline to run the test job `docker pull gradle:6.7-jdk11`

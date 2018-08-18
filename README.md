# README

# Project Name: Realtime Vehicle Location Simulating and Monitoring System

## Author: Cheng Wei

---

## Overview:

Vehicle Location Simulating and Tracking System is a real-time application which can simulate cars' moving path and monitor all the vehicle's real time info including position, direction and speed on the map.

## Features:

* User can see all vechicle's  current positions directly through the Google Map
* User can see vehicle's detailed information such as current direction, speed, vechicle's Id, owner's info and so on through side bar
* User can see the Supply location's \(eg. Gas Station\) detailed info on the Google Map

## System UI:

![](/images/2.jpeg)![](/images/1.jpeg)

## System Architecture:

![](/images/4.jpeg)

### Microserves:

1. Netflix Eureka as service registration and discovery

2. Location Service: to supply the original vehicle's info\(vehicle's status, owner's info, etc\) to the end user and load into Database\(initialization\)

3. Supply Service: to supply the Gas Stations' info to the end user and store it to the database\(initialization\)

4. Location Simulator: to simulation the real-time location updates, it provides REST api for user to start and stop simulator

5. Location Distribution: to disbution the location updates to MessageQueue\(RabbitMQ\)

6. Location Updater: to Consume the locations updates in the MessageQueue, and return the updates to browser through Websocket

7. used Hystrix as circuit breaker  

  Besides, the system incorporated , used Spring Boot Actuator to monitor application health  

## Technology Track:

* Backend: Java, Spring Boot, Spring Data, Spring Cloud, Netflix OSS, SQL, JPA, Maven, Tomcat, WebSocket, RabbitMQ, REST
* Frontend: HTML/CSS, Javascript, Bootstrap
* Databases: MongoDB, H2
* Tools: Git, Docker, Vagrant, IntelliJ IDEA

##   How to run the system:

* Service Start Sequence

  1. docker-compose up
  2. sh ./start-eureka.sh
  3. sh ./start-location-simulator.sh
  4. sh ./start-location-ingest.sh
  5. sh ./start-location-updater.sh
  6. sh ./start-fleet-location-service.sh
  7. go to fleet location service folder and run sh ./upload-fleet.sh
  8. sh./start-supply-location-service.sh
  9. sh ./start-dashboard.sh

* UI

  1. Open Dashboard UI on
     [http://localhost:8080](http://localhost:8080/)
  2. Open Simulator UI on
     [http://localhost:9005](http://localhost:9005/)
  3. Click run button to start simulation
  4. Click stop button to stop simulation
  5. Open Eureka UI on

     [http://localhost:8761](http://localhost:8761/)




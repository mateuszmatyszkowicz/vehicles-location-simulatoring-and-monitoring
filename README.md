#Project Progress check - week 3
##All rights are reserved by Joanne

##Service Start Sequence
1. docker-compose up
3. sh ./start-location-simulator.sh
4. sh ./start-location-ingest.sh
5. sh ./start-location-updater.sh
6. sh ./start-fleet-location-service.sh
7. go to fleet location service folder and run sh ./upload-fleet.sh
8. sh ./start-dashboard.sh

##UI
1. Open Dashboard UI on http://localhost:8080
2. Open Simulator UI on http://localhost:9005
3. Click run simulation
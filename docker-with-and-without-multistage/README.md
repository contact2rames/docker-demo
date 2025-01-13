docker build -t withoutmultistage -f withoutmultiDockerfile .
docker run -it withoutmultistage

docker build -t calc-multi -f multistageDockerfile .
docker run -it calc-multi

To see latest image, run below command:

docker images | head -4

Run the application using: go run calculator.go 

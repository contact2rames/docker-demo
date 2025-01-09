docker build -t withoutmultistage -f withoutmultiDockerfile .

docker build -t calc-multi -f multistageDockerfile .

Run the application using: go run calculator.go

To see latest image, run below command:

docker images | head -4

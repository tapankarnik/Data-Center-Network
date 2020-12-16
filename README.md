# Data Center Network

## Docker
Build the Docker file for the load balancer and the worker. 

    docker build -t load_balancer .
    docker build -t worker worker/.

Get the Stress Testing Subsystem from the following link, [Stress-Testing-Subsytem](https://github.com/tapankarnik/Stress-Testing) and execute the following in the folder.

    docker build -t sts .

## Setting up the network

Use docker compose to set up the network

    docker-compose up

Run the following to take down the network

    docker-compose down

## Testing

### Testing the DCN directly

Send a POST request to localhost:5000/DCN, where the load balancer is accepting requests.
Send a JSON message with 4 parameters, job_name, job_id, num_jobs and job_duration.

### Testing the integrated STS and DCN

Send a POST request to localhost:5011/jobs, where the STS is accepting requests.
Send a JSON message with 4 parameters, job_name, num_jobs and job_duration.


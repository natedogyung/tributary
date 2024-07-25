# Tributary - Ford 
Backend functionality using Flask, Redis, Docker, and Python to accomplish quick engine tempurature readings as well as averge data points


## Docker
Run:

    docker compose up --build

This will start a "tributary" image within docker as well as redis db (6379) and flask (8000) containers to start logging data. 

### POST request endpoints
-------------------------
*I utilized Insomnia to POST data:*

**Current engine tempurature**

    http://0.0.0.0:8000/record | JSON body: {"engine_temperature": 0.7}

*expected output*

    {
	"success": true
    }

**Average engine temperature**

    http://0.0.0.0:8000/collect | empty JSON body

*expected output*

    {
	"average_engine_temperature": 1.174,
	"current_engine_temperature": "7.1"
    }

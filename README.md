# This is a Docker Project - Resumes

This project demonstrates running multiple Dockerized HTML pages using Nginx.  
It shows different resume versions (on-prem and cloud) in separate Docker containers.

`My Resumes/`
├── `Dockerfile.v1`         # Dockerfile for on-prem resume
├── `Dockerfile.v2`         # Dockerfile for cloud resume
├── `html/`
│   ├── `index_v1.html`     # On-prem resume page
│   └── `index_v2.html`     # Cloud resume page
└── `README.md`


## To Run the project I used VS code extension but this can also be done with docker app GUI

1. **Build Docker images we must build docker images 1st with below commands where we created 2 tags as resume_on_prem:local and resume_cloud:local:**

docker build -t resume_onprem:local -f Dockerfile.v1 .
docker build -t resume_cloud:local -f Dockerfile.v2 .

2. **Below commands will Run Docker containers with the tags. If you wanna name the containers, you can use --name option and give the name for that container:**

docker run -d -p 6789:80 resume_onprem:local
docker run -d -p 6790:80 resume_cloud:local

3. **After running the containers you can access resumes at:**

- On-prem resume: http://localhost:6789  
- Cloud resume: http://localhost:6790  

## Notes

- Each container uses Nginx to serve the static HTML pages.
- Ports 6789 and 6790 are mapped for local access.
- You can change the HTML files or Dockerfiles to update the content or ports.
- Docker must be installed locally

## License

This project is open-source and free to use.
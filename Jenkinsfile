stage 'Building nginx Container for Docker Hub'
docker.withRegistry("${registry_url}", "${docker_creds_id}") {
    
    // Set up the container to build
    maintainer_name = "thanh-nguyen"
    container_name = "python-nginx"
 
    stage "Building Container"
    echo "Building nginx with docker.build(${maintainer_name}/${container_name}:${build_tag})"
    container = docker.build("${maintainer_name}/${container_name}:${build_tag}", 'nginx')
   
    // add more tests
    
    stage "Pushing"
    container.push()
    
    currentBuild.result = 'SUCCESS'
}

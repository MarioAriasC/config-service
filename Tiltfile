# Build
custom_build(
    # name of the container image
    ref = 'config-service',
    # Command to build the container image
    command = './gradlew bootBuildImage --imageName $EXPECTED_REF',
    # files to watch that trigger a new build
    deps = ['build.gradle.kts', 'src']
)

# deploy
k8s_yaml(["k8s/deployment.yml", "k8s/service.yml"])

# manage
k8s_resource('config-service', port_forwards=['8888'])
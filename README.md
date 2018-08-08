# global_lib
Jenkins shared global libraries(keep it DRY)


implementation on Jenkinsfile
```
@Library('py_build') _

py_build.info 'Starting'
py_build.warning 'Nothing to do!'
```

### Examples:
```
vars/log.groovy
def info(message) {
    echo "INFO: ${message}"
}

def warning(message) {
    echo "WARNING: ${message}"
}
```

### Jenkinsfile - scripted
```
@Library('utils') _

log.info 'Starting'
log.warning 'Nothing to do!'


Jenkinsfile - Declarative

@Library('utils') _

pipeline {
    agent none
    stage ('Example') {
        steps {
             script { 
                 log.info 'Starting'
                 log.warning 'Nothing to do!'
             }
        }
    }
}
```

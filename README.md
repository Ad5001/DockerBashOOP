# DockerBashOOP
---

Small implementation of Docker for BashOOP.

### Documentation

You can generate the documentation using my [BashDocGenerator](https://git.ad5001.eu/Ad5001/BashDocGenerator).

### How to use

Import the library:
```bash
. $OOP_ROOT/oop.sh

importNamespace "path/to/Docker.shn"
```

**Note**: The guides require to know how to use [BashOOP Objects](https://git.ad5001.eu/Ad5001/BashOOP).

You can store several docker containers in a single Docker.Container object.    
The way it's constructed is using keywords that acts as filter for all current Docker containers (both running and stopped).

For example:    
Find all stopped containers based on the image ubuntu:14:04 :
```bash
Docker.Container c with_image "ubuntu:14.04" stopped
```
**Note**: If you're executing this as a non root user, you may be prompted for your account password in order to access docker data.

A list of all filters can be found in the documentation.

You can see if any object was found using `$c.found`, and the count of containers found using `$c.count`.

You can then access their properties like you would any other object:
```bash
# Their container name
$c.name

# Their container id
$c.id

# Their base image
$c.image

# Amongst others...
# And assign them:
names="$($c.name)"
```

**Note**: When several containers are matched, the value for each container will be put on a new line.

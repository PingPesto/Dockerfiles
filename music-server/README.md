#MPD Docker

Distribution hub of music streams, and centralized controller. Exposes a
controller interface on port 6600, and web/http listener interface on 8000

The container is configured to look for music in /opt/music - which will need
to be volume mounted into the container.

### Run the container:

    docker build -t music .
    docker run -ti --rm -p 8000:8000 -p 6600:6600 -v $HOME/Music:/opt/music music

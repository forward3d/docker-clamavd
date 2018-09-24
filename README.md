# docker-clamavd

ClamAV daemon within an Alpine based Docker image so you can scan files remotely. It uses `supervisord` to run both the `freshclam` virus definition updater and the `clamav` anti-virus processes within the single container. During the build we add virus definitions so that no matter what the container will start with some protections, but upon starting immediately tries to update them.

## Usage

Start the container...

    docker run -d -p 3310:3310 --name clamavd forward3d/clamavd

To scan a file with the container you must have configured your local ClamAV installation with something like...

    TCPSocket 3310
    TCPAddr clamavd

Then it's simply...

    clamdscan eicar2.zip

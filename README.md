# DMIT Mail Server

This project sets up a mail server using the `analogic/poste.io` Docker image.

## Services

### dmit_mail_server

The `dmit_mail_server` service uses the `analogic/poste.io` Docker image to provide a full-featured mail server. It includes support for SMTP, IMAP, and POP3 protocols, as well as a web-based administration interface.

#### Environment Variables

- `TZ`: Sets the timezone for the container.
- `h`: The hostname for the mail server.
- `HTTP_PORT`: The port for HTTP access to the web interface.
- `HTTPS_PORT`: The port for HTTPS access to the web interface.
- `DISABLE_CLAMAV`: Disables the ClamAV antivirus service.

#### Volumes

- `/mnt/mail:/data`: Mounts the host directory `/mnt/mail` to the container's `/data` directory to persist mail data.

#### Networks

- `dmit_network`: Connects the mail server to the `dmit_network` Docker network.

## Usage

To start the mail server, run the following command:

```sh
docker-compose up -d
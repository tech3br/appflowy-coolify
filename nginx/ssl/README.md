# SSL Certificates Directory

Place your SSL certificates in this directory:

- `certificate.crt`: Your SSL certificate
- `private_key.key`: Your private key

**Note**: These files are gitignored for security. 

If you're using Coolify, SSL certificates are handled automatically via Let's Encrypt.

For manual SSL setup:
1. Obtain certificates from your certificate authority or Let's Encrypt
2. Place them in this directory
3. Uncomment the HTTPS server block in `nginx/nginx.conf`
4. Restart nginx: `docker-compose restart nginx`

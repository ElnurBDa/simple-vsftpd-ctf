- https://github.com/raonigabriel/web-terminal - Web Terminal
- https://github.com/ElnurBDa/vulhub/ - vsftpd

```yaml
version: '3'
services:
  web-terminal:
    image: raonigabriel/web-terminal:latest
    ports:
      - "80:7681"
    restart: always
    networks:
      - custom-network
    hostname: getrootflag

  vsftpd:
    build:
      context: ./vsftpd-cve-2011-2523/.
    image: vsftpd-cve-2011-2523
    networks:
      - custom-network
    restart: always
    hostname: gotrootflag

networks:
  custom-network:
    driver: bridge
```

to run it:
```bash
docker compose up -d
```

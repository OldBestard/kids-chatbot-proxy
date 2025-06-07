FROM nginx:alpine

# Create the config using the VPS's actual IP  
RUN echo 'server { \n\
    listen 80; \n\
    server_name _; \n\
    location / { \n\
        proxy_pass http://69.62.80.206:3002; \n\
        proxy_http_version 1.1; \n\
        proxy_set_header Upgrade $http_upgrade; \n\
        proxy_set_header Connection "upgrade"; \n\
        proxy_set_header Host $host; \n\
        proxy_cache_bypass $http_upgrade; \n\
        proxy_set_header X-Real-IP $remote_addr; \n\
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for; \n\
    } \n\
}' > /etc/nginx/conf.d/default.conf

EXPOSE 80

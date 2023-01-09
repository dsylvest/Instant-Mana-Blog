# Instant-Mana-Blog
Using Azure, I built, secured, and protected a cloud application that hosts a cyber blog.

# Created Azure Web App using Azure Free Domains
![image](https://user-images.githubusercontent.com/112778924/211407493-9f38e0c6-1621-4300-be70-11e962a57f59.png)

# Deployed a Docker Container on the Web App using Azure Cloud Shell for Bash
az webapp config container set --name <webapp> --resource-group <resource group> --docker-custom-image-name <container-name> --enable-app-service-storage -t

# Edited my HTML file by using SSH right into the container
[index-html.txt](https://github.com/dsylvest/Instant-Mana-Blog/files/10376936/index-html.txt)

# Created Azure Key Vault to store a self-signed certificate
![image](https://user-images.githubusercontent.com/112778924/211413860-41bb266e-0d5b-48ec-a32b-732e751128a4.png)

# Used OpenSSL to generate a self-signed certificate
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout <privatekeyname.key> -out <certificatename.crt> -addext "extendedKeyUsage=serverAuth"
# Converted my certficate to PFX format for Azure
openssl pkcs12 -export -out <new_certificatename.pfx> -inkey <keyname.key> -in <certificename.crt>

# The above step is not needed for Azure Free Domains as a certificate is supplied. This is only for use of self-owned domains. 

# Created an Azure Front Door and Web Application Firewall to add a custom rule
![image](https://user-images.githubusercontent.com/112778924/211412475-4b03e46a-779f-4486-9499-2a3c4c787a88.png)

# Added a custom WAF rule to deny traffic from three countries
![image](https://user-images.githubusercontent.com/112778924/211412653-9f6a2e91-de4f-43a7-b532-fa0ed703b42b.png)

# Used Microsoft Defender for Cloud to analyze and fix any security recommendations for my cloud resources
Changed access into the web application to require FTPS based on recommendations.

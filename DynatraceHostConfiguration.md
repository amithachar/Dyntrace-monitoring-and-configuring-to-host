# Dyntrace-monitoring-and-configuring-to-host

# Adding host VM to Dynatrace monitoring.

## Search for one agent 

<img width="925" height="709" alt="image" src="https://github.com/user-attachments/assets/e3002817-35fa-4f31-9c9b-fca773bf0620" />

## click one agent 

<img width="1523" height="688" alt="image" src="https://github.com/user-attachments/assets/2e469316-40ab-460e-9dc1-d6d95e7b5f5c" />

## Installation 

<img width="1260" height="823" alt="image" src="https://github.com/user-attachments/assets/0ea64757-a800-4f42-aaab-90e06bb82444" />

## Click on generate api token  ( for new installation you need to generate new api token and install )

<img width="1136" height="562" alt="image" src="https://github.com/user-attachments/assets/ca85413f-74af-46d4-ba70-b0b78ddfbab6" />

### Download OneAgent

```bash
wget -O Dynatrace-OneAgent-Linux-x86-1.329.73.20260123-140641.sh "https://rwr26144.live.dynatrace.com/api/v1/deployment/installer/agent/unix/default/latest?arch=x86" --header="Authorization: Api-Token dt0c01.ID6DTM644MSQFOGHQMEVJNOL.FYWDKSP75ML2F6IKRFHDPEAQY5NSRDKMF5YLODA3FYCNSPVHNLXY36QST6UJHXQ3"
```

### Verify signature

```bash
wget https://ca.dynatrace.com/dt-root.cert.pem ; ( echo 'Content-Type: multipart/signed; protocol="application/x-pkcs7-signature"; micalg="sha-256"; boundary="--SIGNED-INSTALLER"'; echo ; echo ; echo '----SIGNED-INSTALLER' ; cat Dynatrace-OneAgent-Linux-x86-1.329.73.20260123-140641.sh ) | openssl cms -verify -CAfile dt-root.cert.pem > /dev/null
```

### Install OneAgent as the privileged user

```bash
/bin/sh Dynatrace-OneAgent-Linux-x86-1.329.73.20260123-140641.sh --set-monitoring-mode=fullstack --set-app-log-content-access=true
```

### After installing click on deployment status

<img width="219" height="49" alt="image" src="https://github.com/user-attachments/assets/a267170f-c00f-4397-b402-281615f30a70" />

<img width="1365" height="120" alt="image" src="https://github.com/user-attachments/assets/b9d12104-2cbf-4551-a132-5187a4284823" />


### Linux installation procedure.

<img width="1892" height="346" alt="image" src="https://github.com/user-attachments/assets/430756c4-e711-4a9a-97ef-cfc1891df87b" />

<img width="1882" height="355" alt="image" src="https://github.com/user-attachments/assets/120565a7-1eb2-40e7-9c72-38ba3a603d94" />

<img width="1896" height="732" alt="image" src="https://github.com/user-attachments/assets/32afd5aa-2425-4034-9dd0-cd6777c137a9" />

### Monitoring 

<img width="1606" height="780" alt="image" src="https://github.com/user-attachments/assets/c03f16a8-d766-4589-8ef8-54fa4af2d951" />














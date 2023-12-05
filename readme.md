# Setup

creating a templaes/env-secrets.yaml file with the values:
```yaml
apiVersion: v1
kind: Secret
metadata:
  name: {{ .Release.Name }}-secret
type: Opaque
data:
  DATABASE_HOST: {{"[value]" | toString | b64enc }}
  DATABASE_PORT: {{"[value]" | toString | b64enc }}
  DATABASE_NAME: {{"[value]" | toString | b64enc }}
  DATABASE_USER: {{"[value]" | toString | b64enc }}
  DATABASE_PASSWORD: {{"[value]"  | toString | b64enc }}
  TOKEN: {{"[value]" | toString | b64enc }}
```

execute 
```sh
helm install core .
```
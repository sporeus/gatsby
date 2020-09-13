---
title: "Call Center"
metaTitle: "Call Center is the meta title tag for this page"
metaDescription: "This is the meta description for this page"
---

### Repository

[Dashboard (FE + BE)](https://gitlab.bcnfpt.com/platform/fptai-callcenter)
[Voicebot DME](https://gitlab.bcnfpt.com/platform/voicebot-dme)

### Gcloud Repository

- [Frontend](https://console.cloud.google.com/gcr/images/fpt-ai/GLOBAL/callcenter-fe)
- [Backend](https://console.cloud.google.com/gcr/images/fpt-ai/GLOBAL/callcenter)
- [Backend Static](https://console.cloud.google.com/gcr/images/fpt-ai/GLOBAL/callcenter-static)
- [Voicebot DME](https://console.cloud.google.com/gcr/images/fpt-ai/GLOBAL/voicebot-dme)

### Kubernetes

[Fti-Infa (Console, Callcenter-Demo, FPT ID)](https://gitlab.bcnfpt.com/ops/fti-infra)
[HC Callcenter Dashboard](https://gitlab.bcnfpt.com/hmi/hc-infra)
[PCC Infa, PCC Staging Infa](https://gitlab.bcnfpt.com/hmi/pcc-infra)

### FPT ID Install (TODO)

```bash
    Clone repository....
    set up .env
    Create DB, user...
    ALTER USER fptid IDENTIFIED WITH mysql_native_password BY 'jpFptaiv3@Test';

    sudo yum install python3 python3-devel mysql-devel python3-wheel python3-setuptools gcc gcc-c++ kernel-devel make
    python3 -m venv venv
    source venv/bin/activate
    pip install --upgrade pip
    pip install -r requirements.txt
    pip install django-dotenv
    python manage.py migrate
    python manage.py createsuperuser
    python manage.py creatersakey

    Install fptid-static, map port 8001

    Create Client ID
```

```bash
CONSOLE (FPT) hoat dong the nao???

Tich hop FACEBOOK:

Vao trang https://developers.facebook.com/

Vao Settings -> Basic de lay' FACEBOOK_APP_ID va FACEBOOK_APP_SECRET

Add Webhook: Messenger -> Settings -> Webhook -> Add Callback URL -> Nhap: https://bot-jp.fpt.ai/webhook/facebook/ va Verify Token

Test webhook by POSTMAN: POST https://bot-jp.fpt.ai/webhook/facebook/ roi xem log cua bl xem traffic co vao ko???

Test: Vao Webhook ==> Click vao Test, xem log bl, neu' co' 1 cai' nao` bi loi~ la thanh cong, con` neu' ko log ra gi tuc' la .... (Doc lai cho nho' roi xoa'...., viet linh tinh qua')


URL Blocked: This redirect failed because the redirect URI is not whitelisted in the app’s Client OAuth Settings. Make sure Client and Web OAuth Login are on and add all your app domains as Valid OAuth Redirect URIs.
```

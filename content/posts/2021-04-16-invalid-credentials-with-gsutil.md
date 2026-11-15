---
title: 'invalid credentials with gsutil'
author: ulysses

date: 2021-04-16
slug: invalid-credentials-with-gsutil
draft: false
---

If you’re trying to access GCS (Google Cloud Storage) and you’re getting “Your credentials are invalid. Please run gcloud auth login”, you most likely have a previous key stored in the ~/.boto file. This happens if you previously configured gsutil with your own credentials, then switched over to Google SDK mode. To fix the invalid credentials, edit the ~/.boto file and comment out the auth key.

```
vim ~/.boto
```

Comment out.

```
#gs_oauth2_refresh_token = <token redacted="">
</token>
```

Rerun the gsutil ls command. It should work.
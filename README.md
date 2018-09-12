# Odoo cron backup to Google Cloud Storage (GCE)

## How To Use
```
docker run -d -e PROJECT_ID=unique_id_on_gce -e GS_ID=gs_access_key_id -e GS_SECRET=gs_secret_access_key -e ODOO_HOST=127.0.0.1:27017 -e ODOO_DB_NAME=database -e ODOO_MASTER_PASS=password -e BUCKET=storage-bucket -e CRON_TIME="0 1 * * *" hoangphamw/odoo-backup-gce
```

## Environment Variables

#### PROJECT_ID - [Demo(3)](https://storage.googleapis.com/cdn.chessboardradio.com/lab/docker-mongodb-backup-gce/get-storage-keys.png)
The project id on Google Cloud, need be the **default**.

#### GS_ID - [Demo(4)](https://storage.googleapis.com/cdn.chessboardradio.com/lab/docker-mongodb-backup-gce/get-storage-keys.png)
The **Access Key** of Interoperability session.

#### GS_SECRET - [Demo(4)](https://storage.googleapis.com/cdn.chessboardradio.com/lab/docker-mongodb-backup-gce/get-storage-keys.png)
The **Secret Key** of Interoperability session.

#### BUCKET
The bucket name, need create the bucket on Google Cloud Console before.

#### ODOO_HOST
The IP or domain of your Odoo server, with the port (https://odoo.web.server).

#### ODOO_DB_NAME
Database name to backup, the file will be saved at *gs://bucket/database_name_date.tar.gz*.

#### ODOO_USER
If your server need authentication, set the user of current database.

#### ODOO_PASS
Like before but for the password.

#### CRON_TIME
The **cron time**, the frequency that will generate a new backup, default is `0 1 * * *` every day at 1am (GTM).  
Here is a good [cron generator](http://crontab-generator.org/).

## License
None! Use as you want and like.

---

By Jadson Lourenço - [@jadsonlourenco](https://twitter.com/jadsonlourenco)  
*"Quem tem verdadeiros ideais não sonha."*

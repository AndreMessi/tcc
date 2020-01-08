###Men-deploy Aplikasi Golang ke Kubernetes

#membuat project laravel
composer create-project --prefer-dist laravel/laravel my_app

#menjalankan project laravel
php artisan serve

#menggunakan docker compose
sudo apt-get install -y docker.io docker-compose

#membuat dua file menggunakan docker file
app.dockerfile, web.dockerfile

#buat file yml
docker-compose.yml

#atur laravel conf
laravelVHost.conf

#atur env laravel
.env

#jalankan docker compose
docker-compose up -d

#kemudian akses
http://localhost:8080

#lakukan migrate
php artisan migrate


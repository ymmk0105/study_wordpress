# study_wordpress

## 起動
docker compose up -d --build

## 初回インストール
docker compose run --rm wpcli core install --url="http://wp.localhost:8087" --title="WP Local" --admin_user="admin" --admin_password="admin" --admin_email="admin@example.com" --skip-email
docker compose run --rm wpcli language core install ja --activate

## 停止
docker compose down

## DB初期化
docker compose down -v
docker compose up -d --build

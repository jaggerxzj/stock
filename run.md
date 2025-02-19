docker build -f stock/Dockerfile -t mayanghua/instock .

docker run -dit --name InStock -p 9988:9988 -e db_host=host.docker.internal -e db_user=root -e db_password=123456  -e db_database=instockdb -e db_port=3306 --add-host host.docker.internal:host-gateway mayanghua/instock:latest

python instock/job/execute_daily_job.py 2024-01-01 2024-12-31

python instock/job/execute_daily_job.py 2025-01-01 2025-02-19

DIR="./srcs/docker-compose.yml"
DATA_PATH=/home/yaboulan/data

up:
	@echo "Creating necessary directories for volume mounting..."
	@mkdir -p $(DATA_PATH)/mariadb
	@mkdir -p $(DATA_PATH)/wordpress
	@echo "Setting proper permissions..."
	@chmod 777 $(DATA_PATH)/mariadb
	@chmod 777 $(DATA_PATH)/wordpress
	@echo "Starting containers..."
	@docker compose -f $(DIR) up --build -d

down:
	@docker compose -f $(DIR) down

build:
	@docker compose -f $(DIR) build

start:
	@docker compose -f $(DIR) start

stop:
	@docker compose -f $(DIR) stop

ps:
	@docker compose -f $(DIR) ps

fclean:
	@docker compose -f $(DIR) down -v
	@docker system prune -af
	@sudo rm -rf $(DATA_PATH)

re: fclean up

.PHONY: up down build start stop ps fclean re
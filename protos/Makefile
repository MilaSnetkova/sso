# Папка с proto-файлами
PROTO_DIR := proto
GEN_DIR := gen/go

# Список всех .proto файлов
PROTO_FILES := $(wildcard $(PROTO_DIR)/sso/*.proto)

# Цель по умолчанию
default: generate

# Генерация Go-кода из .proto
generate:
	protoc -I $(PROTO_DIR) $(PROTO_FILES) \
		--go_out=$(GEN_DIR) --go_opt=paths=source_relative \
		--go-grpc_out=$(GEN_DIR) --go-grpc_opt=paths=source_relative

# Очистка сгенерированных файлов (опционально)
clean:
	rm -rf $(GEN_DIR)

# Сборка проекта
build:
	go build ./...

# Загрузка зависимостей
mod:
	go mod tidy

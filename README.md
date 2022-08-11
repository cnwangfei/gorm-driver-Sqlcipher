# [GORM Sqlite Driver](https://github.com/go-gorm/sqlite)
GORM Sqlite Driver替换为可加密驱动[go-sqlcipher](github.com/mutecomm/go-sqlcipher/v4)。

修改文件`sqlite.go sqlite_test.go`

## USAGE

```go
import (
Sqlcipher "github.com/cnwangfei/gorm-driver-Sqlcipher"
"gorm.io/gorm"
)

key := "2DD29CA851E7B56E4697B0E1F08507293D761A05CE4D1B628663F411A8086D99"
dbname := fmt.Sprintf("gorm.db?_pragma_key=x'%s'&_pragma_cipher_page_size=4096", key)

//db, err := gorm.Open(sqlite.Open("gorm.db"), &gorm.Config{})
db, err := gorm.Open(Sqlcipher.Open(dbname), &gorm.Config{})
```

Checkout [https://gorm.io](https://gorm.io) for details.

# Örnek JSON Verisi ve Liquibase Changelog

Eğitimlerde sahte REST API ve veritabanı göçü örnekleri için kullanılan iki küçük veri dosyası.

> **Not:** Bu depo 2020 yılında eğitim/örnek amaçlı hazırlandı ve artık güncellenmiyor.

## İçerik

| Dosya | Açıklama |
|---|---|
| `db.json` | `posts` anahtarı altında 62 örnek araç kaydı (`vin`, `brand`, `year`, `color`). json-server biçimindedir; tablo/listeleme bileşenlerini denemek için hazır veri sağlar. |
| `changelog-master.xml` | `TablesAndTables` adlı tek sütunlu bir tablo oluşturan örnek Liquibase changelog dosyası. |

## Kullanım

`db.json` dosyasını json-server ile yerelde REST API olarak sunabilirsiniz:

```bash
npx json-server --watch db.json
```

Kayıtlar `http://localhost:3000/posts` adresinden gelir; `GET`, `POST`, `PUT`, `DELETE` istekleri dosyaya yansır.

`changelog-master.xml` dosyası bir Spring Boot projesinde `spring.liquibase.change-log` ayarıyla ya da
Liquibase komut satırı aracıyla (`liquibase update`) kullanılabilir.

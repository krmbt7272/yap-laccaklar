# Bizim Hikayemiz — Sadece Supabase Ping

Bu paket, gönderilen çalışan `index.html` dosyasını değiştirmeden kullanır.

Eklenen tek sistem:

- `.github/workflows/supabase-daily-ping.yml`
- Her gün Supabase REST API üzerinde `activities` tablosuna salt-okuma isteği gönderir.
- Verileri GitHub'a yedeklemez.
- JSON dosyası oluşturmaz.
- Repoya otomatik commit atmaz.
- Supabase verilerini değiştirmez.

## GitHub'a yükleme

ZIP'i açıp aşağıdaki yapıyı repoya gönder:

```text
index.html
.github/
  workflows/
    supabase-daily-ping.yml
```

Mac'te `.github` klasörü gizli olabilir. Terminal üzerinden repoya kopyalamak veya GitHub'da
`Actions → New workflow → set up a workflow yourself` yoluyla YAML içeriğini eklemek mümkündür.

Workflow GitHub tarafından algılandıktan sonra Actions sekmesinde **Supabase Daily Ping**
adıyla görünür. İlk kontrol için bir kez `Run workflow` ile elle çalıştırılabilir; sonrasında
her gün otomatik çalışır.

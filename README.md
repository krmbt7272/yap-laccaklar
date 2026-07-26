# Bizim Hikayemiz – Güncelleme

## Değişiklikler

- Ana dosya artık `index.html` adındadır.
- Yapılmamış etkinlik başlığı kırmızı, yapılmış etkinlik başlığı yeşildir.
- Yapılmış etkinliklerin üzeri çizilmez.
- Supabase günlük olarak sorgulanır.
- Etkinlikler her gün `data/activities-backup.json` dosyasına yedeklenir.
- Supabase erişilemezse site önce GitHub yedeğini, o da yoksa tarayıcı önbelleğini gösterir.

## GitHub kurulumu

Repo içindeki bütün dosyaları aynı dizin yapısıyla yükleyin.

GitHub reposunda **Settings → Secrets and variables → Actions → New repository secret** bölümüne şunları ekleyin:

- `SUPABASE_URL`: Supabase proje URL'niz
- `SUPABASE_ANON_KEY`: anon/public key'iniz

Ardından **Actions → Supabase Keep Alive and Backup → Run workflow** ile bir kez elle çalıştırın. Başarılı çalışınca mevcut Supabase verileri `data/activities-backup.json` içine otomatik alınır; verileri tekrar girmeniz gerekmez.

## Önemli sınır

GitHub Pages statik bir sistemdir; tarayıcıdan GitHub reposundaki JSON dosyasına güvenli biçimde doğrudan yazılamaz. Bu nedenle yeni etkinlikler Supabase'e yazılmaya devam eder. GitHub JSON dosyası günlük, salt-okunur yedektir.

Workflow günlük API isteği gönderir. Bu yöntem pratikte düzenli aktivite oluşturur; ancak Supabase'in ücretsiz plan politikasında gelecekte yapılabilecek değişikliklere karşı mutlak süreklilik garantisi değildir. En güvenli ücretsiz koruma, günlük GitHub yedeğidir.

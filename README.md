# İskelet Şablonu — Claude Code ile kendi iş sistemini kur

Mesleğin ne olursa olsun (öğretmen, mimar, muhasebeci, avukat, patent vekili, veri analisti, yazılımcı) iyi iş aynı 9 adımla yapılır. Bu klasör o iskelettir: bir "101". Kendi işine göre adım, doküman ve denetçi ekleyip çıkarabilirsin.

## Nasıl başlarım?

1. Bu sayfada **Code → Download ZIP** ile şablonu indir ve ZIP'i aç.
2. Açılan klasörü projelerini tuttuğun yere taşı ve adını işine göre değiştir: küçük harf, tire, boşluk ve Türkçe karakter yok (ör. `ekim-giderleri`). Şablonun kendisinde çalışma; her yeni iş için yeni bir kopya aç.
3. Klasörü Claude Code'da aç: masaüstü uygulamasında **Code** sekmesi → **Choose folder** (VS Code eklentisi ya da terminaldeki `claude` da aynı klasörle çalışır).
4. `/iskelet-kur` yaz. Claude sana işini tek tek soracak, amaç dosyasını ve `CLAUDE.md`'yi senin işine göre dolduracak.
5. Ham malzemeni `girdiler/` klasörüne, gizli belgelerini `ozel/` klasörüne koy. İkisi de GitHub'a gitmez.
6. Dokuz adımla devam et: önce ihtiyaçlar (`docs/01-ihtiyaclar.md`), sonra riskler, yapı, kurallar, plan. Teslimden önce denetçileri çalıştır.

## 9 adım

| # | Adım | Dosya |
| --- | --- | --- |
| 1 | Ne istiyorum? | `docs/00-amac.md`, `docs/01-ihtiyaclar.md` |
| 2 | Neler ters gidebilir? | `docs/02-riskler.md` |
| 3 | Nasıl olacak? | `docs/03-yapi.md`, `docs/taslaklar/` |
| 4 | Benim kurallarım | `docs/04-kurallar.md` (bitti tanımı dahil), `CLAUDE.md` |
| 5 | Neden böyle yaptık? | `docs/kararlar/` |
| 6 | Adım adım plan | `docs/planlar/` |
| 7 | Yap | `ciktilar/` |
| 8 | Kontrol et | `.claude/agents/` (denetçiler) |
| 9 | Ders çıkar | `docs/dersler/` → `docs/04-kurallar.md` |

Her adımda **Claude üretir, sen onaylarsın.** Yeni istekler `01-ihtiyaclar.md` içindeki "Değişiklik talepleri" bölümünden girer.

## Ekip (alt ajanlar)

| Ajan | Görevi | Model · effort |
| --- | --- | --- |
| `tutarlilik-denetcisi` | Dokümanlar ve çıktılar birbiriyle tutarlı mı, her ölçüt karşılanmış mı | Sonnet · high |
| `dokuman-bekcisi` | Silinen/üzerine yazılan bilgi, isim kuralları, referanslar | Haiku · low |
| `guvenlik-denetcisi` | Gizli bilgi, gizlilik, girdi doğrulama | Opus · high |
| `test-denetcisi` | Kabul kriterlerinin (acceptance criteria) testi var mı, testler geçiyor mu | Sonnet · medium |

Hiçbir denetçi dosya değiştiremez; bulur ve raporlar. Ana oturumda model işe göre seçilir: planlarken en güçlü olan, yaparken hızlı olan. Model adları değişir, yöntem değişmez.

## Klasörler

```text
CLAUDE.md          Bu işin anayasası ve doğruluk kuralları; Claude her oturumda okur
.claude/           İzinler, denetçiler, /iskelet-kur tarifi
docs/              İşin hafızası: amaç, ihtiyaçlar, riskler, yapı, kurallar, kararlar, planlar, dersler
girdiler/          Ham malzeme (Claude sadece okur; GitHub'a gitmez)
ozel/              Gizli belgeler (GitHub'a gitmez)
ciktilar/          Teslim edilenler
```

## İzinler

`.claude/settings.json` güvenli bir başlangıç sunar: Claude dosyaları sormadan okuyabilir, `docs/` ve `ciktilar/` altında düzenleme yapabilir; silme, internete erişme ve `git push` için her seferinde sorar; `girdiler/` klasörünü değiştirmesi ve `.env` dosyalarını okuması yasaktır. İhtiyacına göre bu dosyayı düzenleyebilir ya da `/permissions` ile değiştirebilirsin.

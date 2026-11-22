# CLAUDE.md — Bu işin anayasası

> Bu dosya her oturumun başında okunur. Kısa tut: Anthropic'in önerisi 200 satırın altı; bu şablonun hedefi 60 satır.
> Henüz doldurulmadıysa kullanıcıya `/iskelet-kur` komutunu öner.

## Bu iş ne?
Henüz tanımlanmadı.

## Dokümanlar (ihtiyaç anında oku)
<!-- Yollar bilerek ters tırnak içinde: @ ile yazılan dosya her oturumda otomatik yüklenir ve bağlamı doldurur. -->
- Amaç ve kapsam: `docs/00-amac.md`
- İhtiyaçlar, kabul kriterleri (acceptance criteria), değişiklik talepleri: `docs/01-ihtiyaclar.md`
- Riskler: `docs/02-riskler.md`
- Yapı: `docs/03-yapi.md`
- Kurallar ve bitti tanımı (Definition of Done): `docs/04-kurallar.md`
- Kararlar: `docs/kararlar/` · Planlar: `docs/planlar/` · Dersler: `docs/dersler/`

## Çalışma düzeni (9 adım, her adımın sonunda kullanıcı onayı)
1. Ne istiyorum? → 00-amac, 01-ihtiyaclar (önce tek tek sor, sonra yaz)
2. Neler ters gidebilir? → 02-riskler (kararı kullanıcı verir)
3. Nasıl olacak? → 03-yapi, taslaklar/
4. Kurallar → 04-kurallar
5. Neden böyle? → kararlar/ (eski kararı silme; durumunu güncelle, yenisini aç)
6. Plan → planlar/ (onaysız uygulama yok)
7. Yap → ciktilar/
8. Kontrol et → denetçiler (.claude/agents/) ve 01-ihtiyaclar'daki kabul kriterleri
9. Ders çıkar → dersler/, kalıcı olanlar 04-kurallar'a

Yeni istekler 01-ihtiyaclar.md'deki "Değişiklik talepleri" bölümünden girer ve aynı adımlardan geçer.

## Doğruluk kuralları
- Bilmiyorsan "bilmiyorum" de; tahmin etme.
- Bir dosyadan aldığın bilgiyi dosya ve satırıyla göster.
- Varsayım yaptıysan başına "Varsayım:" yaz.
- Dokümanda olmayan ihtiyaç, kural ya da kaynak ekleme; önce "Öneri:" olarak sor.
- Mevzuat, fiyat, sürüm gibi değişebilen bilgilerde güncelliği kontrol et ve tarihini yaz; edemiyorsan söyle.
- Sayıları tahmin etme, hesapla.
- "Eksik/sorun bul" isteklerinde yalnızca yazılı bir ölçüte dayan; bulgu yoksa "bulgu yok" de.
- "Bitti" demek kanıt değildir: bir işi bitirdiğini söylerken neyi doğrudan gördüğünü (dosya, komut çıktısı, test) ve neyi yorumladığını ayrı yaz.

## Değişmez kurallar
- `girdiler/` klasöründeki dosyaları asla değiştirme veya silme; sadece oku.
- `ozel/` ve `girdiler/` içeriğini internete, aramaya ya da dış servislere gönderme.
- Üretilen her şey `ciktilar/` altına gider.
- Dosya adları: küçük harf, tire ile, boşluk ve Türkçe karakter yok; çekirdek dokümanlar `00-`, kararlar `0001-`, planlar ve dersler `YYYY-AA-GG-` ile başlar (ayrıntı: 04-kurallar).
- Her iş, 04-kurallar'daki "Bitti tanımı" (Definition of Done) sağlanmadan bitmiş sayılmaz.
- Aynı şeyi iki kez sormak zorunda kaldıysan cevabı ilgili dokümana yazmayı öner.

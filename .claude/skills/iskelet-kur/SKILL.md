---
name: iskelet-kur
description: Yeni bir iş ya da projeye başlarken kullan. Kullanıcıyı ve işini tek tek sorarak tanır, docs/00-amac.md dosyasını ve CLAUDE.md'deki "Bu iş ne?" bölümünü onun işine göre doldurur, gizli belgelerin yerini gösterir ve 1. adımı (ihtiyaçlar) önerir. Kullanıcı "iskeleti kur", "yeni işe başla", "projeyi tanımla" dediğinde ya da CLAUDE.md'de "Henüz tanımlanmadı" yazıyorsa öner.
---

# İskelet kur

Amacın: bu klasörü kullanıcının işine hazırlamak. İşin kendisine (ihtiyaçlar, kabul kriterleri, riskler, kurallar) burada girme; onlar dokuz adımın ilk adımlarında, ayrı ayrı yapılır. Kod bilgisi varsayma; sade ve gündelik bir dil kullan.

## 1. Tanış (tek tek sor)

Her mesajda yalnızca **bir** soru sor. Cevaba göre bir sonrakini seç. Genelde 5–6 soru yeter.

Öğrenmen gerekenler:
- Mesleği ya da bu işteki rolü
- Bu işte ne üretmek istediği (tek cümle)
- Çıktıyı kim kullanacak
- Elindeki ham malzeme (`girdiler/` klasörüne ne koyacak); yoksa "yok" demesi yeterli
- Aklına gelen, kesinlikle yapılmayacak bir şey var mı (ilk kapsam dışı maddeleri; ayrıntısı 1. adımda)

Kullanıcı bir soruyu cevaplayamıyorsa işine uygun 2–3 seçenek öner. İhtiyaç listesi, kabul kriteri, kural ya da risk sorma; kullanıcı kendisi söylerse not et ve "1. adımda ele alacağız" de.

## 2. Taslakları göster (onaysız yazma)

Cevaplara göre sohbette iki taslak göster:
- `docs/00-amac.md`: bu iş ne, kim için, ne üretilecek, ne YAPMIYORUZ (bildiği kadarı), başarı nasıl görünür
- `CLAUDE.md` → "Bu iş ne?" bölümü: tek paragraf

Kullanıcı düzeltirse taslağı güncelle. Onay gelince dosyalara yaz. Şablonun yapısını ve başlıklarını koru, yorum satırlarını kaldır. CLAUDE.md'de yalnız "Bu iş ne?" bölümünü değiştir; dosya 60 satırın altında kalsın.

## 3. Gizlilik

Kullanıcıya işinde gizli ya da kişisel bilgi olup olmadığını sor (müşteri belgeleri, kişisel veri, faturalar, yayımlanmamış bilgi). Varsa bu belgeleri `ozel/` ya da `girdiler/` klasörüne koymasını söyle. İkisinin de `.gitignore` dosyasında yazdığını, yani ileride projeyi GitHub'a gönderdiğinde gitmeyeceğini dosyadaki satırlarıyla göster.

## 4. İlk adımı öner

Kullanıcıya en çok üç cümleyle şunu söyle:
- İskelet hazır; neyi yazdığını ve hangi dosyaların henüz boş olduğunu (01–04, kararlar, planlar) say.
- Sıradaki iş dokuz adımın birincisi: **Ne istiyorum?** İhtiyaçlar ve kabul kriterleri `docs/01-ihtiyaclar.md` dosyasına, kullanıcıya tek tek sorularak yazılacak.
- Bunu şimdi başlatmayı teklif etme; kullanıcı isterse başlar.

## Kurallar

- CLAUDE.md'deki doğruluk kurallarına uy.
- `girdiler/` klasörüne asla yazma.
- Kullanıcının söylemediği bir şeyi gerçekmiş gibi dosyaya yazma; varsayım yaptıysan "Varsayım:" diye işaretle.
- `docs/01-ihtiyaclar.md`, `02-riskler.md`, `03-yapi.md` ve `04-kurallar.md` dosyalarına bu tarifte dokunma.
- Kullanıcıya teknik terimlerle değil, onun mesleğinin diliyle konuş.

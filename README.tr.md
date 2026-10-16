# Journal Finder Skill (Türkçe)

Yapay zekâ asistanlarının (Claude, ChatGPT) bir makale için hedef dergi seçerken uydurma metrik üretmeden çalışmasını sağlayan, tekrar kullanılabilir bir yöntem.

[English README](README.md)

## Neden

Bir sohbet botuna "bu makaleyi hangi dergiye göndereyim?" diye sorulduğunda genellikle hafızadan bir liste gelir: etki faktörü ve çeyrekler eski ya da yanlış, açık erişim ücreti kontrol edilmemiş, "hızlı" denen derginin hızı tek bir anonim rapora dayanıyor.

Bu skill asistanı tersten çalıştırır:

1. **Adayları yayıncı araçları üretir.** Başlık ve özet Elsevier JournalFinder, Springer Nature Journal Suggester, Wiley Journal Finder, Taylor & Francis Journal Suggester ve JANE'e girilir; ret mektuplarındaki transfer önerileri ve benzer çalışmaların yayımlandığı dergiler eklenir.
2. **Adaylar birleştirilir.** Birden fazla bağımsız aracın önerdiği dergi öne alınır.
3. **Her aday dört bilgi için kaynağından doğrulanır:** indeks (Clarivate Master Journal List), etki faktörü ve **JCR** çeyreği, ücret (APC mi, ücretsiz abonelik yolu mu) ve hız — her hız rakamının kaç rapora dayandığıyla birlikte.
4. **Kapsam ve emsal kontrol edilir:** dergi son yıllarda bu türde çalışma yayımlamış mı?
5. **Kısa, sıralı bir liste** döner; doğrulanamayan her veri işaretlenir, elenen dergiler gerekçesiyle yazılır.

Kararı yazar verir. Asistan önerir; seçmez, göndermez.

## Kaçındığı tuzaklar

- **ESCI ≠ SCIE.** Clarivate 2023'ten beri ESCI dergilerine de etki faktörü veriyor; IF tek başına SCIE kanıtı değildir.
- **SJR çeyreği ≠ JCR çeyreği.** SCImago çeyreği ayrıca etiketlenir, JCR diye sunulmaz.
- **Birden çok JCR kategorisi.** Çeyrek, kategorisiyle yazılır (ör. "Surgery Q1, Orthopedics Q2").
- **n = 1 hız verisi.** Bir-iki rapora dayanan hız rakamı "veri yok" sayılır.
- **Ücretli hızlandırma (fast-track).** Ölçülen hız derginin kendi beyanından belirgin hızlıysa fiyat sayfasına bakılır.
- **Kabul → yayın kuyruğu.** Sayı sıklığı ve online-first yayın kontrol edilir.

## Claude ile kullanım

`skills/journal-finder/` klasörünü skill klasörünüze kopyalayın:

- **Claude Code:** `~/.claude/skills/journal-finder/SKILL.md` (ya da projenin içinde `.claude/skills/`).
- **Claude uygulamaları (claude.ai / masaüstü):** `journal-finder` klasörünü zipleyip *Ayarlar → Capabilities → Skills* altından yükleyin (planınıza bağlı).

Sonra *"Bu makale için hedef dergi bul"* deyip başlık ve özeti yapıştırın. Claude in Chrome (ya da başka bir tarayıcı aracı) varsa Claude yayıncı araçlarını kendisi doldurur; yoksa sonuçlarını yapıştırmanızı ister.

## ChatGPT ile kullanım

[`chatgpt/journal-finder-instructions.md`](chatgpt/journal-finder-instructions.md) dosyasındaki bloğu bir **Custom GPT'nin talimatlarına**, bir **Project'in talimatlarına** ya da sohbetin başına yapıştırın. Web aramasını, varsa Agent modunu/tarayıcıyı açın.

## Kendi eşiğinizi belirleyin

Skill'in sabit bir kalite çıtası yok; başta, her makale için sizinkini sorar. Örnekler:

- "Yalnız SCIE, JCR Q1, APC yok (abonelik yolu)"
- "Scopus, Q1–Q2, APC en fazla 2.000 USD"
- "MEDLINE, çeyrek fark etmez, X yayıncısı olmasın"

## Sınırlamalar

- Clarivate JCR aboneliğe tabidir; çeyrek çoğu zaman yayıncı sayfasından ya da adı verilen ikincil kaynaktan alınır ve öyle işaretlenir.
- Bazı yayıncı araçları bot koruması kullanır. Asistan bunu aşmaya çalışmaz; o aracı sizin çalıştırıp listeyi yapıştırmanız gerekebilir.
- Yayıncı araçları yalnız kendi dergilerini önerir; bu yüzden birkaçı, JANE ve emsal taramasıyla birlikte kullanılır.
- Metrikler her yıl değişir. Göndermeden önce derginin kendi sitesinden mutlaka teyit edin.

## Lisans

MIT — bkz. [LICENSE](LICENSE).

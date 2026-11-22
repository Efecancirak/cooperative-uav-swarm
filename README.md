# Cooperative UAV Swarm with Distributed Task Allocation and Formation Control

**Ders:** Robot Tasarım ve Uygulamaları (2026–2027)
**Konu No:** 21 — Multi-UAV Coordination
**Grup ID:** G__

## 1. Grup Üyeleri

| Ad Soyad | Öğrenci No |
|---|---|
| Efecan Çırak | 032190079 |
| Tolga Babacan | 032190029 |
| Meryem Kiremitçi | 032290116 |
| Şevval Tutaş | 032290115 |

## 2. Amaç, Problem Tanımı ve Kapsam

Bir İHA (UAV) grubunun geniş bir araziyi taraması ve önceden belirlenmiş gözlem bölgelerinden bilgi toplaması hedeflenmektedir. Araçlar birbirine çarpmadan hareket etmeli, ortak görevi aralarında bölüşmeli ve iletişim kısıtları altında koordinasyonu sürdürmelidir. Bir aracın (lider dahil) devre dışı kalması veya bir alt grubun iletişim ağından kopması görevin tamamen durmasına yol açmamalıdır.

**Kapsam / İş paketleri:**
- İP1 — Görev dağıtımı (distributed task allocation)
- İP2 — Formasyon kontrolü ve consensus
- İP3 — Çarpışma önleme ve iletişim modeli
- İP4 — Simülasyon ortamı ve görselleştirme
- İP5 — Deneyler, metrikler ve rapor

## 3. Kullanılacak Yöntemler ve Algoritmalar

- **Görev dağıtımı:** Auction tabanlı yöntemler / CBBA (Consensus-Based Bundle Algorithm)
- **Formasyon kontrolü:** Consensus tabanlı formasyon kontrolü, lider-takipçi yaklaşımı
- **Çarpışma önleme:** Yapay potansiyel alanlar / ayrılma (separation) kuralı
- **İletişim modeli:** Menzil tabanlı iletişim grafiği, mesaj gecikmesi ve kaybı
- **Hata toleransı:** Araç kaybında görevlerin yeniden dağıtılması

## 4. Yöntem Seçim Gerekçeleri ve Alternatifler

_(Merkezi ve dağıtık yaklaşımların karşılaştırılması, neden bu yöntemlerin seçildiği buraya yazılacak.)_

## 5. Sistem Mimarisi ve Çalışma Akışı

_(Mimari diyagram `docs/` klasörüne eklenecek.)_

```
Algılama/Durum  →  İletişim (komşular)  →  Görev Dağıtımı  →  Formasyon + Çarpışma Önleme  →  Hareket
```

## 6. Geliştirme Araçları / Simülasyon Ortamı

- Python 3.10+
- NumPy, Matplotlib (3B noktasal model simülasyonu)
- (Opsiyonel) gym-pybullet-drones — fizik tabanlı 3B doğrulama

## 7. Kurulum ve Çalıştırma

```bash
git clone <repo-url>
cd cooperative-uav-swarm
pip install -r requirements.txt
python simulation/run.py
```

## 8. Testler, Deneyler ve Metrikler

| Deney | Değişken | Metrikler |
|---|---|---|
| Ölçeklenebilirlik | İHA sayısı (3, 5, 10, 20) | Görev süresi, mesaj sayısı |
| Formasyon vs. hızlı tarama | Tarama modu | Kapsama oranı, süre |
| Merkezi vs. dağıtık | Kontrol mimarisi | İletişim yükü, hata toleransı |
| Araç / lider kaybı | Arıza zamanı | Görev tamamlanma oranı |
| İletişim kopması / gecikme | Menzil, gecikme, kayıp oranı | Formasyon hatası, kapsama |

Metrikler: alan kapsama oranı, görev tamamlanma süresi, formasyon hatası, minimum araçlar arası mesafe / çarpışma sayısı, mesaj sayısı.

_(Sonuç grafikleri `results/` klasörüne eklenecek.)_

## 9. Yol Haritası ve İlerleme Günlüğü

| Tarih | Yapılan Çalışma | Mevcut Durum / Sorun | Sonraki Adım |
|---|---|---|---|
| 2026-11-__ | Repository oluşturuldu, konu seçildi | — | Temel simülasyon iskeleti |

## 10. Kaynaklar

_(Ayrıntılı kaynaklar `references/` klasöründe.)_

1. Olfati-Saber, R., Fax, J. A., Murray, R. M. — "Consensus and Cooperation in Networked Multi-Agent Systems", Proceedings of the IEEE, 2007.
2. Choi, H.-L., Brunet, L., How, J. P. — "Consensus-Based Decentralized Auctions for Robust Task Allocation", IEEE Transactions on Robotics, 2009.
3. Reynolds, C. W. — "Flocks, Herds, and Schools: A Distributed Behavioral Model", SIGGRAPH, 1987.

## Klasör Düzeni

```
README.md        Proje tanıtımı ve takip
src/             Kaynak kodlar
simulation/      Çalışan simülasyon
docs/            Rapor ve diyagramlar
results/         Test çıktıları
cv/              Tüm grup üyelerinin CV'leri
requirements.txt Yazılım bağımlılıkları
assets/          Görseller ve veri kaynakları
references/      Araştırma kaynakları ve referanslar
```

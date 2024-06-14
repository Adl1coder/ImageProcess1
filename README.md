# Görüntü İşleme Uygulaması

Bu uygulama, kullanıcıların görüntüleri işlemelerine ve analiz etmelerine olanak tanıyan bir araçtır. Gürültü ekleme, filtreleme, histogram eşitleme ve kenar algılama gibi çeşitli işlemler uygulanabilir.

## Özellikler

- **Gürültü Ekleme**: Görüntülere tuz-biber gürültüsü, Gauss gürültüsü ve spekül gürültüsü ekleyebilme.
- **Filtreleme**: Ortalama filtre, medyan filtre ve Gauss filtre gibi farklı filtrelerle görüntüleri düzeltebilme.
- **Histogram Eşitleme**: Görüntü kontrastını iyileştirmek için histogram eşitleme işlemi yapabilme.
- **Kenar Algılama**: Sobel ve Laplace gibi kenar algılama yöntemleri ile görüntülerdeki sınırları belirleme.
- **Histogram ve Yayılım Eğrileri**: Görüntü piksel dağılımlarını görselleştirmek için histogram ve yayılım eğrileri çizdirme.
- **Eşikleme**: Belirli bir eşik değerine göre görüntüyü siyah ve beyaz olarak sınıflandırma.

## Kullanılan Teknolojiler

- **Python**: Görüntü işleme işlemleri için temel programlama dili.
- **PyQtGraph**: Kullanıcı arayüzü için kullanılan PyQt temelli bir grafik kütüphanesi.
- **OpenCV**: Görüntü işleme algoritmaları ve işlevleri için kullanılan açık kaynaklı kütüphane.

## Kullanım

1. **Görüntü Seçme ve Yükleme**: "File" menüsünden bir görüntü seçin ve yükleyin.
2. **İşlemleri Uygulama**: Seçilen görüntü üzerinde istediğiniz işlemleri seçin ve uygulayın.
3. **Sonuçları Görselleştirme**: Her işlem sonrası güncellenmiş görüntüyü görsel olarak inceleyin.

## Örnek 

```python

import cv2
import numpy as np


image = cv2.imread('image.jpg')


noise = np.zeros(image.shape, np.uint8)
cv2.randu(noise, 0, 255)
salt = noise > 245
pepper = noise < 10
image[salt] = 255
image[pepper] = 0

cv2.imshow('Noisy Image', image)
cv2.waitKey(0)
cv2.destroyAllWindows()

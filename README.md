# Derin-renme-ile-Zat-re-Tespiti

🫁 Pneumonia Detection using Ensemble Deep LearningBu proje, göğüs röntgeni (X-ray) görüntülerinden zatürre (pneumonia) teşhisi koymak için Ensemble (Topluluk) Öğrenme yöntemini kullanan bir derin öğrenme modelidir. MATLAB üzerinde geliştirilmiştir ve 5-katlı çapraz doğrulama (5-fold cross-validation) ile test edilmiştir.🚀 ÖzelliklerÇoklu Model Mimarisi: GoogLeNet, ResNet-18 ve DenseNet-201 modellerinin gücünü birleştirir.Ağırlıklı Oylama (Weighted Ensemble): Modellerin başarı metriklerine (Precision, Recall, F1, AUC) göre dinamik olarak hesaplanan tanh tabanlı ağırlıklandırma sistemi.Veri Artırımı (Data Augmentation): Eğitim setini zenginleştirmek için döndürme, çevirme ve ölçekleme işlemleri.Kapsamlı Analiz: Her model için ayrı ayrı Accuracy, Precision, Recall, F1-Score ve AUC metriklerinin raporlanması.🛠️ Kullanılan TeknolojilerYazılım: MATLAB R2021a veya üzeriToolboxlar:Deep Learning ToolboxComputer Vision ToolboxAutomated Visual Inspection Library (Modeller için)📋 Veri Seti YapısıVeri seti train ve test klasörlerinden oluşmalı ve her klasör altında sınıfları temsil eden alt klasörler bulunmalıdır:textchest_xray/
├── train/
│   ├── NORMAL/
│   └── PNEUMONIA/
└── test/
    ├── NORMAL/
    └── PNEUMONIA/
💻 Kurulum ve ÇalıştırmaBu depoyu klonlayın:bashgit clone https://github.com
MATLAB'i açın ve proje klasörüne gidin.derin_ogrenme.m dosyasındaki dataFolder yolunu kendi bilgisayarınıza göre güncelleyin:matlabrun('derin_ogrenme.m')
📊 Algoritma DetaylarıProje, modellerin tahminlerini basit bir ortalama ile değil, Ağırlıklı Tahmin yöntemiyle birleştirir. Ağırlıklar şu formül ile hesaplanır:\(w=\sum \tanh (Metrics)\)Bu sayede daha güvenilir sonuç veren model, final tahmininde daha fazla söz sahibi olur.📈 Örnek SonuçlarKod çalıştığında modellerin performans karşılaştırmasını içeren bar grafikler ve konfüzyon matrisi otomatik olarak oluşturulur.
Kontrol edilen yol: D:/ysa_kod/archive/chest_xray/chest_xray/train
Sınıflar: NORMAL, PNEUMONIA
Toplam eğitim görüntüsü: 5216
Toplam test görüntüsü: 624

========== FOLD 1/5 ==========
Training DenseNet-121...
Training GoogLeNet...
Training ResNet-18...
Weights - GoogLeNet: 3.0111, ResNet-18: 3.0260, DenseNet: 2.9979
Fold 1 Results:
Ensemble - Acc: 97.32%, Pre: 99.47%, Rec: 96.89%, F1: 98.16%, AUC: 99.79%

========== FOLD 2/5 ==========
Training DenseNet-121..
Training GoogLeNet...
Training ResNet-18...
Weights - GoogLeNet: 3.0149, ResNet-18: 3.0109, DenseNet: 2.9933
Fold 2 Results:
Ensemble - Acc: 96.55%, Pre: 100.00%, Rec: 95.29%, F1: 97.59%, AUC: 99.94%

========== FOLD 3/5 ==========
Training DenseNet-121...
Training GoogLeNet...
Training ResNet-18...
Weights - GoogLeNet: 2.2686, ResNet-18: 2.2745, DenseNet: 2.2713
Fold 3 Results:
Ensemble - Acc: 98.66%, Pre: 99.11%, Rec: 99.11%, F1: 99.11%, AUC: 0.21%

========== FOLD 4/5 ==========
Training DenseNet-121...
Training GoogLeNet...
Training ResNet-18...
Weights - GoogLeNet: 3.0287, ResNet-18: 3.0225, DenseNet: 3.0225
Fold 4 Results:
Ensemble - Acc: 98.27%, Pre: 99.48%, Rec: 98.21%, F1: 98.84%, AUC: 99.92%

========== FOLD 5/5 ==========
Training DenseNet-121...
Training GoogLeNet...
Training ResNet-18...
Weights - GoogLeNet: 3.0143, ResNet-18: 3.0302, DenseNet: 3.0157
Fold 5 Results:
Ensemble - Acc: 98.18%, Pre: 99.74%, Rec: 97.80%, F1: 98.76%, AUC: 99.89%

========== FINAL RESULTS (Mean ± Std) ==========

GoogLeNet:
Accuracy: 96.97% ± 0.81%
Precision: 99.40% ± 0.65%
Recall: 96.50% ± 1.63%
F1-Score: 97.92% ± 0.59%
AUC: 79.91% ± 44.49%

ResNet18:
Accuracy: 97.58% ± 0.96%
Precision: 99.38% ± 0.57%
Recall: 97.36% ± 1.73%
F1-Score: 98.35% ± 0.69%
AUC: 79.91% ± 44.57%

DenseNet121:
Accuracy: 96.22% ± 1.63%
Precision: 99.21% ± 0.52%
Recall: 95.67% ± 2.65%
F1-Score: 97.39% ± 1.18%
AUC: 79.81% ± 44.41%

Ensemble:
Accuracy: 97.80% ± 0.85%
Precision: 99.56% ± 0.33%
Recall: 97.46% ± 1.45%
F1-Score: 98.49% ± 0.61%
AUC: 79.95% ± 44.57%

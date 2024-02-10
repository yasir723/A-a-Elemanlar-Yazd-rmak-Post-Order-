# Ağaç Elemanları Yazdırmak (Post-Order)
`Post-Order gezinme algoritması` kullanarak her bir düğümün değerini önce sol alt ağaç, ardından sağ alt ağaç ve en sonunda kök düğümün değerini yazdırma şeklinde bir sırayla ilerler. Bu yazdırma sonucunda önce ağacın sol tarafındaki düğümleri sonra ağacın sağ tarafındaki düğümleri `en alt düğümden başlayarak yukarıya doğru` şeklinde yazdırılacaktır.

Bu C# sınıfı, binary ağaç veri yapısını oluşturmak için kullanılır
## `tree` Sınıfı

```csharp
class tree
{
    public int value;
    public tree right;
    public tree left;
}
```

### Özellikler

- `value`: Düğümün değerini temsil eder.
- `right`: Düğüme bağlı olan sağ alt düğümü belirtir.
- `left`: Düğüme bağlı olan sol alt düğümü belirtir.

## `yazdır` Metodu
```csharp
static void yazdır(tree node) 
{
    if (node == null) return;

    yazdır(node.left);
    yazdır(node.right);
    Console.WriteLine(node.value);
}
```

## Parametreler

- `node`: Ağaçtaki mevcut düğüm.

## Avantaj

- Ağaçtaki elemanlar önce ağacın sol tarafındaki düğümleri sonra ağacın sağ tarafındaki düğümleri `en alt düğümden başlayarak yukarıya doğru` şeklinde yazdırmayı sağlar.

## İşleyiş
1. İlk olarak gönderilen ağaç null ise, null döndürülür.
2. Null değilse, sola gitmeye başlanır.
3. Null düğüme ulaşana kadar sola gitmeye devam edilir.
3. En sol düğüme ulaşıldığında, sağa bir defa gidilerek tekrar sol düğümlere gidilir.
4. Sol düğüm ve sağ düğüm null olana kadar gezinmeye devam edilir.
5. Sol ve sağ düğümler null ise, `ağacın en solun en derin` düğümüne ulaşılmış olur.
6. Ulaştığı düğümün değeri yazdırılır ve stack'ten çıkılmaya başlanır.
7. Stack'ten çıktıktan sonra sol-sağ-kök sırasına göre yazdırma işlemi gerçekleştirilir.
8. Bu işlem, kökün sol tarafı tamamlandıktan sonra kökün sağ tarafına geçilir ve en sonunda kökün değeri yazdırılır.

<div align="center">
    <h3>Binary Ağaç Elemanları Post-Order Yazdırma Aşamaları</h3>
</div>

[![Yazdırma Adımları](https://github.com/yasir723/Agac-Elemanlari-Yazdirmak-Pre-Order-/assets/111686779/69b40cce-02df-45f7-8453-da0bc03731d7)](https://github.com/yasir723/Agac-Elemanlari-Yazdirmak-Pre-Order-/assets/111686779/69b40cce-02df-45f7-8453-da0bc03731d7)


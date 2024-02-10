# Ağaç Elemanları Yazdırmak (Post-Order)
`Post-Order gezinme algoritması` kullanarak her bir düğümün değerini önce sol alt ağaç, ardından sağ alt ağaç ve en sonunda kök düğümün değerini yazdırma şeklinde bir sırayla ilerler. Bu yazdırma sonucunda ağaçtaki elemanlar en aşağısından yukarıya doğru yazdırılacaktır.

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
static void yazdir(tree node) 
{
    if (node == null) return;

    yazdir(node.left);
    yazdir(node.right);
    Console.WriteLine(node.value);
}
```

## Parametreler

- `node`: Ağaçtaki mevcut düğüm.

## Avantaj

- Ağaçtaki elemanlar `küçükten büyüğe` doğru sıralanmış şekilde yazdırmayı sağlar.

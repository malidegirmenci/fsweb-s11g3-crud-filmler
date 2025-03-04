# HTTP / AJAX II React Modül Projesi: CRUD Film

Bugün CRUD operasyonlarını put, delete, edit requestleri ile yapmayı öğrendiniz. Ayrıca, Route bağlantılı bileşenlere propların nasıl iletileceğini ve bir API'den değer almak için URL parametrelerinin nasıl kullanılacağını araştırdınız. Bu projede, geçen hafta üzerinde çalıştığımız film veritabanı uygulamasına CRUD işlevleri ekleyeceksiniz.

## Giriş

CRUD uygulamaları çoğu web uygulamasının temelidir. Harici bir kaynaktan veri oluşturmayı, düzenlemeyi ve silmeyi yönetebilmek, olabildiğince önemli bir beceridir. Bu projede, tüm bu temel eylemlere izin vermek için gerekli kodu tamamlayacaksınız.

### Kaynak: API dökümanı

#### GET `http://localhost:9000/api/movies`

- Aşağıdaki formatta sunucudaki tüm filmleri getirir.

```
[{
  id: 5,
  title: 'Tombstone',
  director: 'George P. Cosmatos',
  metascore: 89,
  genre: "Drama",
  description: : "A successful lawman's plans to retire anonymously in Tombstone, Arizona are disrupted by the kind of outlaws he was famous for eliminating."
}]
```

#### GET `http://localhost:9000/api/movies/:id`

- Girilen id'ye sahip filmi getirir.

#### POST `http://localhost:9000/api/movies`

- Body de aktarılan bilgilerle yeni bir film ekler. **Güncellenmiş movie listesini döndürür.**

#### PUT `http://localhost:9000/api/movies/:id`

- Girilen id li filmin body deki bilgilerini günceller. **Güncellenmiş film listesini döndürür.**

#### DELETE `http://localhost:9000/api/movies/:id`

- Girilen id deki filmi listeden siler. **Silinen filmin id sini döndürür.**

**_Görevlerinizi tek tek tamamladığınızdan ve ilerlemeden önce her bir görevi test ettiğinizden emin olun.._**

## Talimatlar

### Görev 1: Proje Kurulumu

- [X] Forklayın.
- [X] Klonlayın.
- [X] Proje dizinine girin
- [X] `npm install`
- [X] `npm start`

### Görev 2: Proje Gereksinimleri

#### Film düzenleme

- [X] Öncelikle, filmi düzenle bileşenine gidebilmemiz gerekiyor. App.js içinde, `<EditMovieForm> ` bileşenine edit route unu ekleyin.

- [X] Ardından, url aracılığıyla bileşene iletilen idyi almamız gerekiyor.. id yi almak için `useParams` hookunu kullanın.

- [X] Mevcut filmin niteliklerini yerel form stateimize yükleyebilmeliyiz. `EditMovieForm` bağlandığında, mevcut idmizin filmini api'den alın ve yerel state'e döndürülen verileri kaydedin.

- [X] Bu noktada, düzenleme formu gönderildiğinde hiçbir şey olmuyor. Sunucuyu güncellenmiş film verilerimizle güncellemek için gereken api çağrısını ekleyin.

- [X] Sunucu verilerinizin ve yerel state'inizin senkronize olduğundan emin olmayı unutmayın! Düzenleme formuna, uygulamanın "setMovies" metoduna erişim izni vermek için düzenleme yapmak için gereken değişiklikleri yapın.

- [X] Artık `setMovies`e erişimimiz olduğuna göre, güncellenmiş film listesinin global state'imize kaydedildiğinden emin olun.

- [X] Kullanıcıyı halihazırda düzenlenen filmin bağımsız bilgi sayfasına yönlendirin.

#### Film silme

> _Bir CRUD özelliği eklediniz! Aferin! Şimdi film silme özelliği ekleyelim._

- [X] Silmek için gereken "butonu" tutan bileşeni tanımlayın. Bu butona bir event handler ekleyin.

- [X] Görüntülenmekte olan filmi silmek için istekte bulunan bir event handler oluşturun. Bu requestten ne döndürüldüğünü gözlemleyin.

- [X] Bir kez daha sunucuyu ve state verilerini senkronize tutmanız gerekecek. `App.js` içinde, `deleteMovie` metodunu bir id alıp, girilen id li filmi verimizden silip state'i güncelleyecek şekilde tamamlayın.

- [X] `deleteMovie` 'yi ilgili bileşene aktarın.

- [X] Film silme isteği yapıldığında `deleteMovie` yi çalıştırın, istek tamamlandığında kullanıcıyı `/movies` routeuna yönlendirin.

#### Yeni bir film ekleme

> _Tamam! Artık hazırsın! Şimdi baştan sona bir CRUD oluşturalım._

- [X] Sıfırdan bir "AddMovieForm" bileşeni oluşturmak için "EditMovieForm.js"yi model olarak kullanın. Bileşen, yeni bir filmin tüm özelliklerini yerel state'de tutmalıdır.

- [X] `AddMovieForm`'a erişim sağlayan bir route ekleyin.

- [X] Kullanıcı arayüzünün yeni "AddMovieForm"unuza yönlendirilmesi gereken bölümünü bulun. Bu düğmenin beklendiği gibi çalışmasını sağlayın.

- [X] AddMovieForm'da, form gönderimi için bir event handler ekleyin. Form gönderildiğinde, bileşenin state değerleri ile bir film eklemek için uygun çağırıyı çalıştırın.

- [X] Bileşeninizin, oluşturulduktan sonra genel state'inin `/movies` dizinine yönlendirmeler için gerekli erişime sahip olduğundan ve bunları çalıştırdığından ve değiştirdiğinden emin olun.

### Esnek görevler

- [X] "addToFavorites" işlevini ekleyin. `Film` bileşeninde favori butonuna basıldığında, o anda görüntülenenin idsinin ve adının `App.js`deki favori state diliminde olduğundan emin olun.
- [X] Ekstra kredi için, yalnızca benzersiz filmlerin favori olarak eklenebildiğinden emin olun. Diziler için ".find" metodunu nasıl kullandığımızı hatırlayın.
- Projeye gece modu ekleyin.

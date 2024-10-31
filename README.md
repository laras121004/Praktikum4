# Praktikum4
Implementasikan java code diagram class berikut:

![image](https://github.com/user-attachments/assets/0ead166d-fb8e-4619-a3e7-8e2cb9167599)

- Class BangunDatar
  
 ~~~
package bangundatar;

abstract class BangunDatar {
    abstract float keliling();
       
    }
  ~~~

<p>Class BangunDatar adalah class abstrak yang memiliki metode keliling() yang juga abstrak. Artinya, keliling() tidak memiliki implementasi di sini dan harus diimplementasikan oleh subclass yang mewarisi BangunDatar.</p>

## class Lingkaran
  
```
 package bangundatar;
public class Lingkaran extends BangunDatar {
   private int r;
    
   public  Lingkaran(int r){
        this.r = r;
    }

    float luas() {
       return (float) (Math.PI *r*r);
    }

    @Override
    float keliling() {
        return (float) (2*Math.PI*r);
    }
    
}
```

<p>Mendefinisikan kelas bernama Lingkaran. Kelas Lingkaran mewarisi (menurunkan) kelas BangunDatar, yang merupakan kelas abstrak. Karena BangunDatar memiliki metode abstrak luas() dan keliling(), Lingkaran harus mengimplementasikan metode-metode tersebut. Menginisialisasi nilai r (jari-jari) ketika objek Lingkaran dibuat lalu Menetapkan nilai parameter r ke atribut r di dalam kelas, sehingga nilai jari-jari disimpan di objek Lingkaran. Rumus untuk luas lingkaran adalah π × r². Dalam Java, kita menggunakan Math.PI untuk nilai π. Rumus untuk keliling lingkaran adalah 2 × π × r. Kita gunakan Math.PI untuk nilai π.</p>

## class Segitiga

```
  package bangundatar;
  public class Segitiga extends BangunDatar{
    private int alas, tinggi;
    
    public Segitiga(int alas, int tinggi){
        this.alas = alas;
        this.tinggi = tinggi;
        
    }

   
    public float luas() {
       return (float) (0.5*alas*tinggi);
    }

    @Override
    public float keliling() {
        //keliling segitiga membutuhkan panjang sisi-sisinya
        // asumsikan ini adalah segitiga siku-siku
        float sisiMiring = (float) Math.sqrt(alas*alas*tinggi*tinggi);
        return (float)(alas+tinggi+sisiMiring);
        
      }
    }
 ```

<p> Class Segitiga adalah subclass dari BangunDatar yang menghitung luas dan keliling segitiga siku-siku menggunakan alas dan tinggi yang diberikan.</p>

## class Persegi

```
package bangundatar;

public class Persegi extends BangunDatar {
    private int sisi;
    
    public Persegi(int sisi){
        this.sisi = sisi;
    }

   public float luas() {
       return(float)(sisi*sisi);
        
    }

    @Override
    public float keliling() {
        return(float)(4*sisi);
    }
    
}

```

<p>Kelas `Persegi` dalam kode Java ini merupakan turunan dari kelas `BangunDatar` yang bertujuan untuk menghitung luas dan keliling persegi. Atribut `sisi` menyimpan panjang sisi persegi dan diinisialisasi melalui konstruktor `Persegi(int sisi)`. Metode `luas` menghitung luas dengan rumus \( \text{sisi} \times \text{sisi} \), sementara metode `keliling` menggunakan rumus \( 4 \times \text{sisi} \) untuk keliling. Kedua metode tersebut mengembalikan hasil dalam tipe `float`, dengan casting `(float)` untuk memastikan tipe data yang konsisten.</p>

## clas Main

```
package bangundatar;

public class Utama {

    abstract class BangunDatar {
        abstract float luas();
        abstract float keliling();
    }

    class Lingkaran extends BangunDatar {
        int r;

        Lingkaran(int r) {
            this.r = r;
        }

        @Override
        float luas() {
            return (float) (Math.PI * r * r);
        }

        @Override
        float keliling() {
            return (float) (2 * Math.PI * r);
        }
    }

    class Segitiga extends BangunDatar {
        int alas;
        int tinggi;

        Segitiga(int alas, int tinggi) {
            this.alas = alas;
            this.tinggi = tinggi;
        }

        @Override
        float luas() {
            return (float) (0.5 * alas * tinggi);
        }

        @Override
        float keliling() {
            double sisiMiring = Math.sqrt((alas / 2.0) * (alas / 2.0) + tinggi * tinggi);
            return (float) (alas + 2 * sisiMiring);
        }
    }

    class Persegi extends BangunDatar {
        int sisi;

        Persegi(int sisi) {
            this.sisi = sisi;
        }

        @Override
        float luas() {
            return sisi * sisi;
        }

        @Override
        float keliling() {
            return 4 * sisi;
        }
    }

    public static void main(String[] args) {
        Utama program = new Utama();
        
        Lingkaran lingkaran = program.new Lingkaran(7);
        System.out.println("Luas Lingkaran: " + lingkaran.luas());
        System.out.println("Keliling Lingkaran: " + lingkaran.keliling());

        Segitiga segitiga = program.new Segitiga(10, 15);
        System.out.println("Luas Segitiga: " + segitiga.luas());
        System.out.println("Keliling Segitiga: " + segitiga.keliling());

        Persegi persegi = program.new Persegi(5);
        System.out.println("Luas Persegi: " + persegi.luas());
        System.out.println("Keliling Persegi: " + persegi.keliling());
    }
}
```

<p> Kode di atas mendefinisikan class `Utama` yang berisi beberapa class turunan dari class abstrak `BangunDatar`: `Lingkaran`, `Segitiga`, dan `Persegi`. Masing-masing class turunan mengimplementasikan metode `luas()` dan `keliling()` sesuai dengan rumus masing-masing bentuk geometris. Class `Lingkaran` menggunakan jari-jari `r` untuk menghitung luas dan keliling lingkaran, class `Segitiga` menggunakan alas dan tinggi untuk menghitung luas dan keliling segitiga (diasumsikan sebagai segitiga siku-siku), dan class `Persegi` menggunakan panjang sisi untuk menghitung luas dan keliling persegi. Pada method `main`, objek dari masing-masing class (`Lingkaran`, `Segitiga`, dan `Persegi`) dibuat, lalu luas dan keliling dari setiap objek dicetak di konsol.</p>

## Output
![](Outup.png).




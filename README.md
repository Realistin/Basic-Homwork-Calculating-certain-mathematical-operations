<!DOCTYPE html>
<html lang="tr">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Görev 2 - Kesir Hesaplama</title>
    <script>
      class Kesir {
        constructor(pay, payda) {
          this.pay = pay;
          this.payda = payda;
        }

        // Kesirleri toplama
        static toplama(k1, k2) {
          let pay = k1.pay * k2.payda + k2.pay * k1.payda;
          let payda = k1.payda * k2.payda;
          return Kesir.sadeleştir(new Kesir(pay, payda));
        }

        // Kesirleri çıkarma
        static cikarma(k1, k2) {
          let pay = k1.pay * k2.payda - k2.pay * k1.payda;
          let payda = k1.payda * k2.payda;
          return Kesir.sadeleştir(new Kesir(pay, payda));
        }

        // Kesirleri çarpma
        static carpma(k1, k2) {
          let pay = k1.pay * k2.pay;
          let payda = k1.payda * k2.payda;
          return Kesir.sadeleştir(new Kesir(pay, payda));
        }

        // Kesirleri bölme
        static bolme(k1, k2) {
          let pay = k1.pay * k2.payda;
          let payda = k1.payda * k2.pay;
          return Kesir.sadeleştir(new Kesir(pay, payda));
        }

        // Kesri sadeleştirme
        static sadeleştir(kesir) {
          const gcd = (a, b) => (b == 0 ? a : gcd(b, a % b));
          let ortak = gcd(kesir.pay, kesir.payda);
          kesir.pay /= ortak;
          kesir.payda /= ortak;
          return kesir;
        }

        // Kesir yazdırma
        yazdir() {
          console.log(`${this.pay} / ${this.payda}`);
        }
      }

      let kesir1 = new Kesir(2, 3);
      let kesir2 = new Kesir(4, 5);

      console.log("Toplama:");
      Kesir.toplama(kesir1, kesir2).yazdir();

      console.log("Çıkarma:");
      Kesir.cikarma(kesir1, kesir2).yazdir();

      console.log("Çarpma:");
      Kesir.carpma(kesir1, kesir2).yazdir();

      console.log("Bölme:");
      Kesir.bolme(kesir1, kesir2).yazdir();
    </script>
  </head>
  <body>
    <h1>Görev 2: Kesir Hesaplama</h1>
  </body>
</html>

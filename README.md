# Lab10Web
**Nama	 : Siti Latifah** <br>
**NIM	   : 312010321** <br>
**Kelas	 : TI.20.A2** <br>
**Matkul : Pemrograman Web** <br>

# PHP OOP
Buat file baru dengan nama mobil.php
``` php
<?php
// program sederhana pendefinisian class dan pemanggilan class

class Mobil {

    private $warna;
    private $merk;
    private $harga;

    public function __construct() {
        $this->warna = "Biru";
        $this->merk = "BMW";
        $this->harga = "10000000";
    }

    public function gantiWarna ($warnaBaru)
    {
        $this->warna = $warnaBaru;
    }

    public function tampilWarna ()
    {
        echo "Warna Mobilnya : " . $this->warna;
    }
}

// membuat objek mobil
$a = new Mobil();
$b = new Mobil();

// memanggil objek
echo "<b>Mobil pertama</b><br>";
$a->tampilWarna();
echo "<br>Mobil pertama ganti warna<br>";
$a->gantiWarna("Merah");
$a->tampilwarna();

// memanggil objek
echo "<br><b>Mobil kedua</b><br>";
$a->gantiWarna("Hijau");
$a->tampilwarna();

?>
```
## OUTPUT
![Screenshot (330)](https://user-images.githubusercontent.com/73010098/172304419-9d8eca0b-8e13-4322-9522-19bfc18bce0a.png)

Buat file baru dengan nama form.php
``` php
<?php
// Nama class : form
// Deskripsi class untuk membuat form inputan text sederhana

class Form 
{
    private $fields = array();
    private $action;
    private $submit = "submit Form";
    private $jumField = 0;

    public function __construct($action, $submit)
    {
        $this->action = $action;
        $this->submit = $submit;
    }

    public function displayForm()
    {
        echo "<form action='".$this->action."' method='POST'>";
        echo '<table width="100%" border="0">';
        for ($j=0; $j<count($this->fields); $j++) {
            echo "<tr><td
align='right'>".$this->fields[$j]['label']."</td>";
            echo "<td><input type='text'
name='".$this->fields[$j]['name']."'></td></tr>";
    }
    echo "<tr><td colspan='2'>";
    echo "<input type='submit' value='".$this->submit."'></td></tr>";
    echo "</table>";
} 

public function addField($name, $label)
{
    $this->fields [$this->jumField]['name'] = $name;
    $this->fields [$this->jumField]['label'] = $label;
    $this->jumField ++;
}
}
?>
```

Buat file baru dengan nama form_input.php
``` php
<?php
/**
* Program memanfaatkan Program 10.2 untuk membuat form inputan sederhana.
**/
include "form.php";
echo "<html><head><title>Mahasiswa</title></head><body>";
$form = new Form("","Input Form");
$form->addField("txtnim", "Nim");
$form->addField("txtnama", "Nama");
$form->addField("txtalamat", "Alamat");
echo "<h3>Silahkan isi form berikut ini :</h3>";
$form->displayForm();
echo "</body></html>";
?>
```
## OUTPUT
![Screenshot (332)](https://user-images.githubusercontent.com/73010098/172304463-50648823-e423-4227-8707-83486529dc1a.png)




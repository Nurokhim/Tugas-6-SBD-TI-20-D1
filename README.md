<table>
  <tr>
    <td>NAMA</td>
    <td>Nurokhim</td>
  </tr>
  <tr>
    <td>NIM</td>
    <td>312010064</td>
  </tr>
  <tr>
    <td>KELAS</td>
    <td>TI.20.D1</td>
  </tr>
  <tr>
    <td>MATKUL</td>
    <td>Sistem Basis Data</td>
  </tr>
 <tr>
    <td>DOSEN</td>
    <td> Muhammad Najamuddin Dwi Miharja, S.Kom, M.kom, </td>
  </tr>
</table>

<b>Tugas 6</b>
 
 1.Masuk ke databse nama_nim

![image](https://user-images.githubusercontent.com/101801920/171457747-5eebbaff-d4d3-4bed-9dbc-e9a065075731.png)

untuk memulai backup dan recovery kita pastkan terlebih dahulu bahwa isi dari database sebelumnya ada, yait dengan cara melihatnya di <b>desc nurokhim_312010064;</b>

dan <b>show tables;</b>

![image](https://user-images.githubusercontent.com/101801920/171466032-df10018b-9485-43d1-924e-ae58431d1e42.png)

2. Lakukan proses backup dan recovery dengan sql dari database tugas seblumnya !

pastikan lakukan penguncian(lock) terlebih dahulu kepada data yang akan di backup sebeum mem backup

![image](https://user-images.githubusercontent.com/101801920/171467193-75d97125-2132-46a9-a89e-a0ddfcbfd7fb.png)

a. Kemudian backup table dengan perintah : <i>SELECT * INTO OUTFILE 'backup_</i>(nama data yang akan di backup) <i>FROM</i>(nama data yang akan di backup);

![image](https://user-images.githubusercontent.com/101801920/171468256-5ea96e77-3275-4ef7-b9c5-38418a0aa464.png)

Buktikan file backup anda sukses dengan melihat pada direktori C:\xampp\mysql\data\nurokhim_312010064

![image](https://user-images.githubusercontent.com/101801920/171470649-925a69f4-aa5c-48dd-9d04-c394ba20539f.png)

b. Melakukan Proses Recovery/Restore

Untuk memastikan langkah backup berhasil, selanjutnya hapus table dengan peritah <i>DELETE FROM</i> nurokhim_312010064;

Kemudian pilih table tadi dengan perintah <i>SELECT * FROM</i> nurokhim_312010064; dan pastikan table kosong (empty set)





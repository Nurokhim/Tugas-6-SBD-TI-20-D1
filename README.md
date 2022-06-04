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

a. Kemudian backup table dengan perintah : <i>SELECT * INTO OUTFILE </i>('nama data yang akan di backup') <i>FROM</i>(nama data yang akan di backup);

![image](https://user-images.githubusercontent.com/101801920/171468256-5ea96e77-3275-4ef7-b9c5-38418a0aa464.png)

Buktikan file backup anda sukses dengan melihat pada direktori C:\xampp\mysql\data\nurokhim_312010064

![image](https://user-images.githubusercontent.com/101801920/171470649-925a69f4-aa5c-48dd-9d04-c394ba20539f.png)

b. Melakukan Proses Recovery/Restore

Untuk memastikan langkah backup berhasil, selanjutnya hapus table dengan peritah <i>DELETE FROM</i> nurokhim_312010064;

![image](https://user-images.githubusercontent.com/101801920/171523789-565d8a60-9a92-443f-bcff-a36fbab0d63a.png)

Kemudian pilih table tadi dengan perintah <i>SELECT * FROM</i> nurokhim_312010064; dan pastikan table kosong (empty set)

![image](https://user-images.githubusercontent.com/101801920/171523955-0c924066-027c-4bc2-8562-8da6f7b0f6e6.png)

Selanjutnya lakukan recovery data tadi dengan sql dengan perintah <i>LOAD DATA INFILE</i> ('nama data yang akan di recovery')

<i>INTO TABLE</i>('nama data yang akan di recovery');

![image](https://user-images.githubusercontent.com/101801920/171524803-22e490bc-f00d-4218-8a53-e3c27c4e402b.png)

Kemudian kita buktikan dengan perintah <i>SELECT * FROM</i> nurokhim_312010064; , untuk memastikan data ter recover kembali.

![image](https://user-images.githubusercontent.com/101801920/171525178-7cc06fd9-19b8-4e70-8e7e-1a862b13ec00.png)

3. Lakukan proses backup dan recovery dengan sqldump dari database tugas sebelumnya!

a. Jalankan shell atau commad-prompt dan ketikkan perintah berikut untuk memulai dump database MySQLDUMP –u root –p nurokhim_312010064 >

backup2_nurokhim_312010064.sql

![image](https://user-images.githubusercontent.com/101801920/171526088-9f57ae04-a676-4f66-b29e-1c819c58126b.png)

b. Data yang telah di-backup dapat di restrore kembali ke dalam database dengan perintah mysqldump -u root -p  nurokhim_312010064 <

c:\xampp\mysql\bin\backup2_deniluqmantoro_312010071.sql

![image](https://user-images.githubusercontent.com/101801920/171527272-5bd84ea8-1568-4dd4-bcfa-f2c703456ade.png)

![image](https://user-images.githubusercontent.com/101801920/171527359-bd2cbdf3-f5f7-4e00-93d4-150702f16d16.png)

![image](https://user-images.githubusercontent.com/101801920/171527402-9984b1c3-267b-4ba9-a4c6-9ce22af12cb5.png)

![image](https://user-images.githubusercontent.com/101801920/171527449-cd29d5df-2d55-4ced-b23c-31a4c997fba0.png)

4. Tulisakan script cron job untuk melakukan backup otomatis setiap hari minggu jam 12 malam!

crontab –e

0 0 * * 7myqldump -u root -p nurokhim_312010064>nurokhim_312010064_backup.sql

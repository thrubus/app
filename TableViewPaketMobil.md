### Table View Paket Mobil

```sql
CREATE VIEW v_paket_mobil AS SELECT
pm.idpaket_mobil,
pm.radius_idradius AS pm_idradius,
pm.paket_biaya_idpaket_biaya AS pm_idpaket_biaya,
pm.item_layanan_iditem_layanan AS pm_iditem_layanan,
pm.tipe_mobil_kisaran_harga_idtipe_mobil_kisaran_harga AS pm_idkisaran_harga,
pm.harga,
r.idradius,
r.km_radius,
r.durasi_perjalanan,
r.minimum_pesan,
r.keterangan AS r_keterangan,
pb.idpaket_biaya,
pb.nama_paket,
pb.satuan,
pb.jumlah,
pb.range_jumlah_min,
pb.range_jumlah_max,
pb.makspilih,
pb.jenis_paket,
pb.batas_jam,
pb.status,
il.iditem_layanan,
il.nama,
il.keterangan AS il_keterangan,
il.alias AS il_alias,
ip.iditem_paket,
ip.nama_paket AS ip_nama_paket,
ip.alias AS ip_alias,
tmkh.idtipe_mobil_kisaran_harga,
tmkh.nama_kisaran_harga,
tmkh.harga_min,
tmkh.harga_max
FROM paket_mobil AS pm
LEFT JOIN radius AS r ON r.idradius = pm.radius_idradius
LEFT JOIN paket_biaya AS pb ON pb.idpaket_biaya = pm.paket_biaya_idpaket_biaya
LEFT JOIN item_layanan AS il ON il.iditem_layanan = pm.item_layanan_iditem_layanan
LEFT JOIN item_paket AS ip ON ip.iditem_paket = pb.item_paket_iditem_paket
LEFT JOIN tipe_mobil_kisaran_harga AS tmkh ON tmkh.idtipe_mobil_kisaran_harga = pm.tipe_mobil_kisaran_harga_idtipe_mobil_kisaran_harga
```
### Table View Mobil

``` sql
CREATE VIEW v_mobil AS SELECT
m.idmobil,
m.nopol,
m.no_rangka,
m.ac AS m_ac,
m.tv AS m_tv,
m.karaoke AS m_karaoke,
m.dvd AS m_dvd,
m.wifi AS m_wifi,
m.cc AS m_cc,
m.seat AS m_seat,
m.masa_berlaku_stnk AS m_masa_berlaku_stnk,
m.th_pembuatan AS m_th_pembuatan,
m.tgl_daftar AS m_tgl_daftar,
m.mitra_idmitra AS m_idmitra,
m.tipe_mobil_idtipe_mobil AS m_idtipe_mobil,
m.item_status_mobil_iditem_status_mobil AS m_iditem_status_mobil,
m.item_warna_iditem_warna AS m_iditem_warna,
m.item_bahan_bakar_iditem_bahan_bakar AS m_iditem_bahan_bakar,
mt.*,
tm.*,
ibb.*,
ism.*
FROM mobil AS m
LEFT JOIN mitra AS mt ON mt.idmitra = m.mitra_idmitra
LEFT JOIN tipe_mobil AS tm ON tm.idtipe_mobil = m.tipe_mobil_idtipe_mobil
LEFT JOIN item_bahan_bakar AS ibb ON ibb.iditem_bahan_bakar = m.item_bahan_bakar_iditem_bahan_bakar
LEFT JOIN item_status_mobil AS ism ON ism.iditem_status_mobil = m.item_status_mobil_iditem_status_mobil
```
``` sql 
CREATE VIEW v_mobil AS SELECT 
m.*,
tm.nama_mobil,
tm.idtipe_mobil,
mt.idmitra,
ibb.nama_bahan_bakar,
ism.nama AS nama_status_mobil,
iw.warna,
p.idpool,
pmd.driver_iddriver
FROM mobil AS m
JOIN tipe_mobil AS tm ON tm.idtipe_mobil = m.tipe_mobil_idtipe_mobil
JOIN mitra AS mt ON mt.idmitra = m.mitra_idmitra
JOIN item_bahan_bakar AS ibb ON ibb.iditem_bahan_bakar = m.item_bahan_bakar_iditem_bahan_bakar
JOIN item_status_mobil AS ism ON ism.iditem_status_mobil = m.item_status_mobil_iditem_status_mobil
JOIN item_warna AS iw ON iw.iditem_warna = m.item_warna_iditem_warna
JOIN pool AS p ON p.idpool = mt.pool_idpool
LEFT JOIN ploting_mobil_driver AS pmd ON pmd.mobil_idmobil = m.idmobil
```
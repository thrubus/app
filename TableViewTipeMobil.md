>
CREATE VIEW v_tipe_mobil AS
SELECT 
`idtipe_mobil`, 
`kategori_mobil_idkategori_mobil` AS `tm_idkategori_mobil`, 
`tipe_mobil_kisaran_harga_idtipe_mobil_kisaran_harga` AS `tm_idkisaran_harga`, 
`item_bahan_bakar_iditem_bahan_bakar` AS `tm_iditem_bahan_bakar`, 
`nama_mobil`, 
`pintu`, 
`ac`, 
`karaoke`, 
`tv`, 
`toilet`, 
`smok_area`, 
`rasio_bahan_bakar`, 
`tonase`, 
`masa_berlaku_kir_mulai`, 
`masa_berlaku_kir_akhir`, 
`masa_berlaku_stnk`, 
`masa_berlaku_kps`, 
`panjang_bax`, 
`lebar_bax`, 
`tinggi_bax`,
km.*,
kh.*,
ibb.iditem_bahan_bakar,
ibb.nama_bahan_bakar,
ibb.harga,
ibb.item_satuan_iditem_satuan AS ibb_iditem_satuan
FROM tipe_mobil AS tm
LEFT JOIN kategori_mobil AS km ON km.idkategori_mobil = tm.kategori_mobil_idkategori_mobil
LEFT JOIN tipe_mobil_kisaran_harga AS kh ON kh.idtipe_mobil_kisaran_harga = tm.tipe_mobil_kisaran_harga_idtipe_mobil_kisaran_harga
LEFT JOIN item_bahan_bakar AS ibb ON ibb.iditem_bahan_bakar = tm.item_bahan_bakar_iditem_bahan_bakar
>
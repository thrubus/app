
# SQL Find Paket Layanan

``` sql
SELECT pm.*,r.*,il.nama_layanan FROM `paket_mobil` AS pm
JOIN radius AS r ON r.idradius = pm.`radius_idradius`
JOIN item_layanan AS il ON il.iditem_layanan = pm.`item_layanan_iditem_layanan`
WHERE pm.`paket_biaya_idpaket_biaya` = 3
AND r.km_radius >= 330
```
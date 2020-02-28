
# SQL Find Paket Layanan

``` sql
SELECT pm.*,r.* FROM `paket_mobil` AS pm
JOIN radius AS r ON r.idradius = pm.`radius_idradius`
WHERE pm.`paket_biaya_idpaket_biaya` = 3
AND r.km_radius >= 330
```
# 2-motion-sensors-and-1-light
En lille YAML-script som anvender trigger ID, således at tænd og sluk funktion kan være i en automation
Denne automation virker, når solen ikke længere er over horisonten, dvs når det er mørkt. 
<p>En af sensorerne registrer en bevægelse -> tænd lys<br>
En af sensorerne registrer ingen bevægelse længere -> sluk lys efter 3 minutter (default IKEA værdi, som er hardcoded i sensoren)</p>

Fejl! Hvis der er registreret bevægelse og solen er skiftet til over horisonten, så slukker lyset ikke..., da udløseren bevægelse er stoppet aldrig bliver udløst
Så de nye betingelser er:
1) Sol er over horisonten og lyset er tændt
2) Sol er under horisonten
<p>Visning i brugergrænseflade</p>

![image](https://user-images.githubusercontent.com/103023823/198015505-5aa6042f-2111-4588-bcf5-755066c2a495.png)

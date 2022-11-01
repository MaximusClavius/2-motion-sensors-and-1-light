# 2-motion-sensors-and-1-light

## Det er noget skrammel
Udklip af historikken fra området: Gang + sun.sun
![Skærmbillede 2022-11-01 075949](https://user-images.githubusercontent.com/103023823/199177495-ae3647a2-2cdc-4f7e-8b98-5840aae262b7.png)
Der er 2 problemer i denne konstruktion:
1. Sensor 2 tænder og slukker lyset, og ignorer sensor 1
2. Sensor 1 vil slukke lyset, men solen er over horisonten, og lyset bliver ikke slukket
<p><b>DER ER DØMT TÆNKEBOKS</b></p>

En lille YAML-script som anvender trigger ID, således at tænd og sluk funktion kan være i en automation
Denne automation virker, når solen ikke længere er over horisonten, dvs når det er mørkt. 
<p>En af sensorerne registrer en bevægelse -> tænd lys<br>
En af sensorerne registrer ingen bevægelse længere -> sluk lys efter 3 minutter (default IKEA værdi, som er hardcoded i sensoren)</p>

Fejl! Hvis der er registreret bevægelse og solen er skiftet til over horisonten, så slukker lyset ikke..., da udløseren bevægelse er stoppet aldrig bliver udløst
Så de nye betingelser er:
1) Sol er over horisonten og lyset er tændt <b>eller</b>
2) Sol er under horisonten
<p>Visning i brugergrænseflade</p>

![image](https://user-images.githubusercontent.com/103023823/198015505-5aa6042f-2111-4588-bcf5-755066c2a495.png)

# 2-motion-sensors-and-1-light
En lille YAML-script som anvender trigger ID, således at tænd og sluk funktion kan være i en automation
Denne automation virker, når solen ikke længere er over horisonten, dvs når det er mørkt. 
<p>En af sensorerne registrer en bevægelse -> tænd lys<br>
En af sensorerne registrer ingen bevægelse længere -> sluk lys efter 30 sekunder</p>

Fejl! Hvis der er registreret bevægelse og solen er skiftet til over horisonten, så slukker lyset ikke..., da udløseren bevægelse er stoppet aldrig bliver udløst
![image](https://user-images.githubusercontent.com/103023823/198010779-3e57695c-78e7-4ae9-bb46-679f28826589.png)

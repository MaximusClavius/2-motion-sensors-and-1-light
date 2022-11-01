# 2-motion-sensors-and-1-light

## Det er noget skrammel
<p>Oprindelige ide: En lille YAML-script som anvender trigger ID, således at tænd og sluk funktion kan være i en automation
Denne automation virker, når solen ikke længere er over horisonten, dvs når det er mørkt.</p>
<p><b>Udløsere:</b><br>
En af sensorerne registrer en bevægelse -> tænd lys<br>
En af sensorerne registrer ingen bevægelse længere -> sluk lys efter 3 minutter (default IKEA værdi, som er hardcoded i sensoren)</p>
<p><b>Betingelser:</b><br>
Sol er over horisonten og lyset er tændt<br>
&emsp;<i>eller</i><br>
Sol er under horisonten</p>
<p><b>Handlinger:</b><br>
<i>Choose:</i><br>
ligth-on: tænd lys<br>
ligth-off: sluk lys
</p>
Udklip af historikken fra området: Gang + sun.sun

![Skærmbillede 2022-11-01 075949](https://user-images.githubusercontent.com/103023823/199177495-ae3647a2-2cdc-4f7e-8b98-5840aae262b7.png)
<del>Der er 2 problemer i denne konstruktion</del> Nej, der er 3 problemer i denne konstruktion:
1. Sensor 2 tænder og slukker lyset, og ignorer sensor 1 (Trigger ID kan åbenbart ikke være ens for sensorer)
2. Sensor 1 vil slukke lyset, men solen er over horisonten, og lyset bliver ikke slukket.
3. Ingen udløser til at slukke lyset i dagslys. En IKEA sensor sender kun en motion-off, når der er konstateret en motion-on og det sker efter 3 minutter (default IKEA værdi, som er hardcoded i sensoren)
<p><b>DER ER DØMT TÆNKEBOKS</b></p>
Når jeg ved der er 3 minutter colddown før en motion-off, så kunne man ersatte motion-off med en timer, som slukker lyset efter 3-4 minutter. Får at sensorerne til at samarbejde skal de i samme gruppe.
<p><b>Udløsere:</b><br>
En af sensorerne registrer en bevægelse -> tænd lys<br>
Timer udløber -> sluk lys<br>
<p><b>Betingelser:</b><br>
Sol er over horisonten og lyset er tændt<br>
&emsp;<i>eller</i><br>
Sol er under horisonten</p>
<p><b>Handlinger:</b><br>
<i>Choose:</i><br>
ligth-on: tænd lys og start eller genstart timer<br>
ligth-off: sluk lys
</p>
<p>Visning i brugergrænseflade<br>
Hvis man fjernede det gamle bras (de deaktiverede), så blev det til en lille fin automation.<br>
En Hjælper>Gruppe samlede bevægelsessensorene i "Udløsere", og fik dem til at samarbejde om bevægelse on/off.<br>
En Hjælper>Timer fik lyset til at slukke hver eneste gang - dog afhængig af Betingelser.<br>
Trigger ID bevirkede af Handlinger blev reduceret til 2, nemlig 1) tænd lys og timer og 2) sluk lys.<br>
Alternativt kunne man droppe timeren, og bruge gruppen som trigger til både "on"/"off" for bevægelsessensorer fremfor kun "on".</p>

![image](https://user-images.githubusercontent.com/103023823/199212389-9ebfb6ff-a760-4bb1-8a37-95adc60ea122.png)

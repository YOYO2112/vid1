<!DOCTYPE html>
<html>
<head>

</head>

<body>
    
<?php
require ("conexion.php");
$conexion=mysql_connect($db_host, $db_usuario, $db_contraseña);
if (mysql_connect_error()){
    echo "Fallo al conectar con la base de datos";
    exit();
}


mysql_select_db($conexion,$db_nombre) or die ("no se encuentra base de datos");
mysql_set_charset($conexion,"utf8");
$consulta="SELECT * FROM videos";
$resultados="mysqli_query($conexion,$consulta)

while ($fila=mysql_fetch_array($resultados))
{

        $nombre=$fila ['nombre'];
        $sinopsis=$fila ['sinopsis'];
        $url=$fila ['url'];

        echo("<h1>$nombre</h1>");
        echo("<h2>$sinopsis</h2>");
        echo("<video src='$url' controls='controls' width='450' height='450/>'");


}
mysqli_close($conexion);
?>



</body> 
</html>

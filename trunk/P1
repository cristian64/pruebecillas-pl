#! /bin/bash

# Pruebas de entrada y salida.
echo "-------------------------------------------------";
echo "        PL - Pruebas de la práctica 1";
echo "-------------------------------------------------";
echo

$(javac *.java)

pruebas=$(ls pruebas/pruebas*.ent);
for i in $pruebas
{
	# El fichero ejecutable es $i.
	# El fichero con la salida del ejecutable es $i, quitandole el .ent y añadiendole .sal.
	salida="";
	salida=$(echo $i | cut -d '.' -f 1);
	salida=$salida".sal";
	
	echo "Comprobando $i $salida";
	
	$(rm -f salida);
	$(rm -f aux);
	
	$(java Main $i 2>>salida 1>>salida);
	diff salida $salida -b;

	if ([ $? == 0 ]) then
		echo "[OK]";
	else
		echo "[ERROR]";
	fi
	echo;
}

$(rm -f salida);
$(rm -f aux);

echo;
echo "-------------------------------------------------";
echo "                     FIN";
echo "-------------------------------------------------";
echo;



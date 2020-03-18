#!/bin/bash
while :
do
clear
echo -en "\e[92m"
figlet CORTEZ
echo -en "\e[91m"
figlet NETFREE
echo -en "\e[92mCREATE BY:\e \e[92mCORTEZ\e"
echo ""
echo ""
echo -en "\e[92m1)\e \e[91mBUSCAR HOSTS\e"
echo ""
echo ""
echo -en "\e[92m2)\e \e[93mESCANEAR PUERTOS\e"
echo ""
echo ""
echo -en "\e[95m3)\e \e[91mIP GEOLOCALIZACION\e"
echo ""
echo ""
echo -en "\e[97m4)\e \e[93mCHECKEAR ESTATUS DEL HOST\e"
echo ""
echo ""
echo -en "\e[91m0)\e \e[97mSALIR DEL SCRIPT\e"
echo ""
echo ""
echo -en -n "\e[96mSELECIONE SU OPCION : "
read opcion
case $opcion in
1)clear
echo -en "\e[97m"
figlet BUSCADOR
echo -en "\e[96m"
figlet DE HOST
echo -en -n "\e[95mINGRESE EL HOST : "
echo -en "\e[96m"
read host
echo ""
sleep 2
echo -en "\e[92mBUSCANDO HOSTS..."
sleep 2
echo ""
echo ""sleep 2
echo -en "\e[96mLISTO!"
echo ""
echo ""
curl http://api.hackertarget.com/hostsearch/?q=$host
sleep 2
echo ""
echo ""
echo -en "\e[91mPRESIONE ENTER PARA CONTINUAR"
read foo
;;
2)clear
echo -en "\e[97m"
figlet ESCANEAR
echo -en "\e[96m"
figlet PUERTOS
echo -en -n "\e[95mINGRESE SU HOST : "
echo -en "\e[96m"
read host
echo ""
sleep 2
echo -en "\e[92mESCANEANDO PUERTOS DEL HOST..."
echo ""
sleep 2
echo ""
echo -en "\e[96mLISTO!"
echo ""
echo ""
curl http://api.hackertarget.com/nmap/?q=$host
sleep 2
echo ""
sleep 2
echo -en "\e[91mPRESIONE ENTER PARA CONTINUAR"
read foo
;;
3)clear
echo -en "\e[97m"figlet CHECKEAR
echo -en "\e[96m"
figlet GEO IP
echo -en -n "\e[95mINGRESE EL IP/HOST : "
echo -en "\e[96m"
read host
echo ""
sleep 2
echo -en "\e[92mBUSCANDO GEOLOCALIZACION DEL HOST..."
echo ""
echo ""
sleep 2
echo -en "\e[96mLISTO!"
echo ""
echo ""
curl http://api.hackertarget.com/geoip/?q=$host
sleep 2
echo ""
echo ""
echo -en "\e[91mPRESIONE ENTER PARA CONTINUAR"
read foo
;;
4)clear
echo -en "\e[97m"
figlet ESTATUS
echo -en "\e[96m"
figlet DEL HOST
echo -en -n "\e[95mINGRESE SU HOST : "
echo -en "\e[96m"
read host
echo ""
sleep 2
echo -en "\e[92mCOMPROBANDO ESTATUS DEL HOST INGRESADO..."
echo ""
sleep 2
echo ""
echo -en "\e[96mLISTO!"
echo ""
echo ""
curl http://api.hackertarget.com/httpheaders/?q=$host
sleep 2echo ""
echo -en "\e[91mPRESIONE ENTER PARA CONTINUAR"
read foo
;;
5)clear
echo -en "\e[96m"
figlet CREDITOS
echo ""
echo -en "\e[95mLEYENDO..."
echo ""
echo ""
sleep 2
echo -en "\e[96mLISTO!"
echo ""
echo ""
sleep 2
cat creditos.txt
echo ""
echo -en "\e[91mPRESIONE ENTER PARA CONTINUAR"
read foo
;;
0)clear
echo -en "\e[96m"
figlet EXIT...
echo ""
echo -en "\e[95mCERRANDO EL SCRIPT..."
echo ""
echo ""
sleep 2
echo -en "\e[92mESPERE..."
echo ""
echo ""
sleep 2
echo -en "\e[96mLISTO!"
sleep 2
clear
echo -en "\e[97m"
ls
exit 0
;;*)clear
echo -en "\e[96m"
figlet UPS...
echo ""
echo -en "\e[95mCOMANDO INVALIDO"
echo ""
echo ""
sleep 2
echo -en "\e[92mREINICIANDO SCRIPT..."
echo ""
echo ""
sleep 2
echo -en "\e[96mLISTO!"
sleep 2
bash host.sh
;;
esac
done

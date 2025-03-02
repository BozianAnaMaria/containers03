# Docker
# Scop
Aceasta lucrare de laborator familiarizează cu elementele de bază ale containerizării și pregătește spațiul de lucru pentru următoarele lucrări de laborator.
# Sarcina
Instalarea Docker Desktop și verificarea funcționării acestuia.


# Executare
de catre: Bozian Ana-Maria
ziua: 02.03.2025
1. am creat repozitoriul containers03 si l-am clonat in git hub cu ssh key
2. am creat fisierul dockerfile cu urmatorul cotinut:
FROM debian:latest
COPY ./site/ /var/www/html/
CMD ["sh", "-c", "echo hello from $HOSTNAME"]
3. in containers03 am facut directoriul site unde am adaugat index.html
![Screenshot 2025-03-02 214205](https://github.com/user-attachments/assets/0a752d85-6204-4d5c-a6c8-2a99ed217361)


# Pornire, Testare si raspuns la intrebari 
1. executam comanda:
docker build -t containers03 .
![Screenshot 2025-03-02 224824](https://github.com/user-attachments/assets/78adb079-cd2f-4c2b-81e7-d15110ba7a7f)
## Cât timp a durat crearea imaginii?
mai mult de un minut.

2. executam comanda de mai jos pentru a porni containerul:
docker run --name containers03 containers03
## Ce a fost afișat în consolă?
mesaj de salut 
![image](https://github.com/user-attachments/assets/0144a05c-aade-45b8-989d-b45ea437f8a7)

3. stergem containerul si il pornim inca odata folosind urmatoare comenzi:
docker rm containers03
docker run -ti --name containers03 containers03 bash
![image](https://github.com/user-attachments/assets/6d48a712-3918-4703-b006-fac08de83301)

4. executam comenzile
cd /var/www/html/
ls -l
## Ce este afișat pe ecran?
![image](https://github.com/user-attachments/assets/8f402c7b-598c-4044-a8cf-33f6283fa90e)
-rwxr-xr-x: Permisiunile fișierului:
rwx: proprietarul (root) poate citi, scrie și executa fișierul.
r-x: membrii grupului pot citi și executa fișierul, dar nu pot modifica.
r-x: oricine altcineva poate citi și executa fișierul, dar nu poate modifica.
fisierul este gol.

5. inchidem fereastra cu comanda exit.
   ![image](https://github.com/user-attachments/assets/25614ba2-1569-485d-8a03-8fd70e43b211)

# Bibliografie 
https://app.docker.com/ 
https://help.ubuntu.com/community/FilePermissions

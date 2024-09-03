![Resultado_consulta_DNS_com_comando_dig](https://github.com/user-attachments/assets/a6f0f50d-facd-4b1a-ac20-c9cf45ef7f6d)<br>
Imagem que exibe o resultado de uma consulta DNS usando o comando *dig* para o domínio *google.com*<br><br>


Na imagem acima podemos ver que o comando *dig* foi usado para consultar o servidor DNS local (127.0.0.53), que responde com o endereço de IP
correspondente ao domínio *google.com* (142.251.129.78). Nela podemos ver detalhes como:<br>
- Consulta feita pelo comando *dig*: ```QUESTION SECTION: google.com.			IN	A```
- Resposta do Servidor DNS ("traduz" *google.com* para o *endereço IP* 142.251.129.78.): ```ANSWER SECTION: google.com.		149	IN	A	142.251.129.78```
- Tempo da consulta: ```Query time: 5 msec```
- Servidor DNS usado: ```SERVER: 127.0.0.53#53(127.0.0.53) (UDP)```
- Horário em que a consulta foi feita: ```WHEN: Tue Sep 03 17:55:46 -03 2024```

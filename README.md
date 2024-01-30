### Máscara de CPF/CNPJ com jQuery

#### Objetivo:
Adicionar uma máscara de CPF/CNPJ a um campo de input utilizando a biblioteca jQuery Mask.

#### Como funciona:
O código utiliza a biblioteca jQuery Mask para formatar dinamicamente o input do CPF ou CNPJ enquanto o usuário digita.

#### Instruções para a Equipe:

1. **Inclusão do jQuery Mask:**
   - Certifique-se de incluir a biblioteca jQuery Mask no projeto.
   - Utilize o seguinte script no head do HTML para incluir a biblioteca:

     ```html
     <script
       src="https://cdnjs.cloudflare.com/ajax/libs/jquery.mask/1.14.16/jquery.mask.min.js"
       integrity="sha512-pHVGpX7F/27yZ0ISY+VVjyULApbDlD0/X0rgGbTqCE7WFW5MezNTWG/dnhtbBuICzsd0WQPgpE4REBLv+UqChw=="
       crossorigin="anonymous"
       referrerpolicy="no-referrer"
     ></script>
     ```

2. **Configuração da Máscara de CPF/CNPJ:**
   - Adicione o seguinte script JavaScript para configurar a máscara:

     ```javascript
     $(document).ready(function () {
       var options = {
         onKeyPress: function (value, e, field, options) {
           var masks = ['000.000.000-000', '00.000.000/0000-00'];
           var mask =
             value.replace(/\D/g, '').length > 11 ? masks[1] : masks[0];
           $('.cpf-cnpj').mask(mask, options);
         },
       };
       $('.cpf-cnpj').mask('000.000.000-000', options);
     });
     ```

3. **Uso no Campo de CPF/CNPJ:**
   - Adicione a classe `cpf-cnpj` ao campo de input que deseja aplicar a máscara.
   - Por exemplo, para o campo de CPF:

     ```html
     <input type="text" class="cpf-cnpj" placeholder="Digite seu CPF">
     ```

   - A máscara será aplicada automaticamente enquanto o usuário digita.

4. **Funcionamento da Máscara:**
   - A máscara identifica dinamicamente se o valor digitado representa um CPF ou CNPJ e formata de acordo.

5. **Observações:**
   - Certifique-se de que a versão da biblioteca jQuery Mask seja compatível com as necessidades do projeto.

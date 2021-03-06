jQuery-CPF-CNPJ-Validator-plugin
================================

Um plugin jQuery para validar CPF ou CNPJ, ou quem sabe os dois...

<span>Indique o campo que deseja validar:</span>
<code>$('.validar').cpfcnpj();</code>
<br/><br/>
<h6>Tipo a ser validado (CPF, CNPJ ou os dois)</h6>
Para definir o tipo de valor esperado: <code>validate</code> podendo ser <code>'cpf'</code>, <code>'cnpj'</code> ou <code>'cpfcnpj'</code> para os dois valores. Default: <code>'cpfcnpj'</code>
<br/><br/>
<h6>Máscara</h6>
Se desejar máscara no campo, apenas adicione ao ```<head>``` o <a href="http://igorescobar.github.io/jQuery-Mask-Plugin/">jQuery-Mask-Plugin</a> e defina <code>mask: true</code>. Se o campo for do tipo <code>'cpfcnpj'</code> a mascara será definida conforme digitação do usuário. Default: <code>false</code>
<br/><br/>
<h6>Quando validar</h6>
Para definir em que evento deve acontecer a validação: <code>event</code> podendo ser qualquer evento jQuery, exemplo: <code>click</code>, <code>focusout</code> ou qualquer outro evento. Default: <code>focusout</code>
<br/><br/>
<h6>Qual elemento deve disparar a validação</h6>
Use <code>handler</code> podendo ser qualquer valor de um seletor jQuery, exemplo: <code>'#btn'</code> ou <code>'input'</code>, etc. Default: <code>o elemento a ser validado</code>
<br/><br/>
<h6>O que fazer se o valor for VÁLIDO?</h6>
Essa function será executada se o valor passar pela validação definida.
Defina uma function em:
<code>ifValid</code>. Caso esteja usando <code>validate: 'cpfcnpj'</code> pode ser recuperado o tipo do valor inserido pelo usuário apenas adicionando um parâmetro, exemplo: <code>function (tipo)</code>. Será retornada uma string <b>'cpf'</b> ou <b>'cnpj'</b>
<br/><br/>
<h6>O que fazer se o valor for INVÁLIDO?</h6>
Essa function será executada se o valor NÃO passar pela validação definida.
Defina uma function em:
<code>ifInvalid</code> podendo exibir um alert, definir o foco, o que quiser...
<br/>
<h5>Exemplo:</h5>
```
$(document).ready(function () {
	$('.validar').cpfcnpj({
		mask: true,
		validate: 'cpfcnpj',
		event: 'click',
		handler: '.btn',
		ifValid: function (type) { alert(type); },
		ifInvalid: function () { alert('invalid'); }
	});
});
```

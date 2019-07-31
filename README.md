# irrigador-autom-tico- 
<p>O Regador Autom&aacute;tico &eacute; um rob&ocirc; que monitora quando uma planta est&aacute; com "sede". O qual, por meio de sensores de umidade do solo, de baixo custo. O invento tem o objetivo de usar tecnologia, de forma respons&aacute;vel, para irrigar plantas com o menor consumo de &aacute;gua, dispensa ainda o trabalho humano no processo de irrigar.</p>
<h1>Irrigador automatico</h1>
<p>O Irrogador Autom&aacute;tico &eacute; um rob&ocirc; que monitora quando uma planta est&aacute; com "sede". O qual, por meio de sensores de umidade do solo, de baixo custo. O invento tem o objetivo de usar tecnologia, de forma respons&aacute;vel, para irrigar plantas com o menor consumo de &aacute;gua, dispensa ainda o trabalho humano no processo de irrigar.</p>
<h1><strong>Montagem</strong></h1>
<p>Para fazer o sistema de irriga&ccedil;&atilde;o com arduino, utilizaremos uma v&aacute;lvula solenoide de entrada de &aacute;gua,&nbsp;modelo VA05-12V. Ela funciona com uma tens&atilde;o de 12V DC.Pode ser utilizada em sistemas de irriga&ccedil;&atilde;o, abastecimento e muitas outras aplica&ccedil;&otilde;es. O fluido utilizado (&aacute;gua, etc.) deve ter a temperatura at&eacute; 60&ordm;C.</p>
<h2>Materiais Necess&aacute;rios</h2>
<ul>
<li>1 Unidade &ndash; Arduino Uno</li>
<li>1 Unidade &ndash; Sensor de Umidade de Solo</li>
<li>1 Unidade &ndash; Modulo Rele 5V</li>
<li>1 Unidade &ndash; Jumper Femea Macho</li>
<li>1 Unidade &ndash; Jumper Macho Femea</li>
<li>1 Unidade &ndash; Valvula Solenoide para Agua 12V VA 05</li>
<li>1 Unidade &ndash; Fonte 12V/1A</li>
<li>1 Unidade &ndash; Adaptador P4 Femea</li>
<li>1 Unidade &ndash; Mangueira</li>
<li>1 Unidade &ndash; Terminal Faston f&ecirc;mea (opcional)</li>
<li>1 Unidade &ndash; Ferro de Solda e Estanho (opcional)</li>
</ul>
<h2>Programa&ccedil;&atilde;o</h2>
<p>O sketch para este projeto encontra-se abaixo:</p>
<div id="crayon-5d4201ed85f15799278526-7" class="crayon-line"><span class="crayon-r">int</span> <span class="crayon-v">valvula</span> <span class="crayon-o">=</span> <span class="crayon-cn">8</span><span class="crayon-sy">;</span> <span class="crayon-c">// sinal do rele para v&aacute;lvula</span></div>
<div id="crayon-5d4201ed85f15799278526-8" class="crayon-line crayon-striped-line">&nbsp;</div>
<div id="crayon-5d4201ed85f15799278526-9" class="crayon-line"><span class="crayon-t">void</span> <span class="crayon-st">setup</span><span class="crayon-sy">(</span><span class="crayon-sy">)</span> <span class="crayon-sy">{</span></div>
<div id="crayon-5d4201ed85f15799278526-10" class="crayon-line crayon-striped-line"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-st">pinMode</span><span class="crayon-sy">(</span><span class="crayon-v">valvula</span><span class="crayon-sy">,</span> <span class="crayon-k">OUTPUT</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span> <span class="crayon-c">// declara v&aacute;lvula como sa&iacute;da</span></div>
<div id="crayon-5d4201ed85f15799278526-11" class="crayon-line"><span class="crayon-sy">}</span></div>
<div id="crayon-5d4201ed85f15799278526-12" class="crayon-line crayon-striped-line">&nbsp;</div>
<div id="crayon-5d4201ed85f15799278526-13" class="crayon-line"><span class="crayon-t">void</span> <span class="crayon-st">loop</span><span class="crayon-sy">(</span><span class="crayon-sy">)</span> <span class="crayon-sy">{</span></div>
<div id="crayon-5d4201ed85f15799278526-14" class="crayon-line crayon-striped-line">&nbsp;</div>
<div id="crayon-5d4201ed85f15799278526-15" class="crayon-line"><span class="crayon-c">// Leitura do sensor no pino A0 e armazenamento em SensorValue</span></div>
<div id="crayon-5d4201ed85f15799278526-16" class="crayon-line crayon-striped-line">&nbsp;</div>
<div id="crayon-5d4201ed85f15799278526-17" class="crayon-line"><span class="crayon-r">int</span> <span class="crayon-v">sensorValue</span> <span class="crayon-o">=</span> <span class="crayon-st">analogRead</span><span class="crayon-sy">(</span><span class="crayon-v">A0</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div>
<div id="crayon-5d4201ed85f15799278526-18" class="crayon-line crayon-striped-line">&nbsp;</div>
<div id="crayon-5d4201ed85f15799278526-19" class="crayon-line"><span class="crayon-c">// verifica se valor de leitura est&aacute; acima de 600 (umido abaixo de 600&nbsp;&nbsp;e seco at&eacute; 1023)</span></div>
<div id="crayon-5d4201ed85f15799278526-20" class="crayon-line crayon-striped-line">&nbsp;</div>
<div id="crayon-5d4201ed85f15799278526-21" class="crayon-line"><span class="crayon-st">if</span> <span class="crayon-sy">(</span><span class="crayon-v">sensorValue</span> <span class="crayon-o">&gt;</span> <span class="crayon-cn">600</span><span class="crayon-sy">)</span><span class="crayon-sy">{</span></div>
<div id="crayon-5d4201ed85f15799278526-22" class="crayon-line crayon-striped-line"><span class="crayon-h">&nbsp;&nbsp; </span><span class="crayon-c">// se sim, libera &aacute;gua por 1s</span></div>
<div id="crayon-5d4201ed85f15799278526-23" class="crayon-line"><span class="crayon-h">&nbsp;&nbsp; </span><span class="crayon-st">digitalWrite</span><span class="crayon-sy">(</span><span class="crayon-v">valvula</span><span class="crayon-sy">,</span><span class="crayon-k">LOW</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div>
<div id="crayon-5d4201ed85f15799278526-24" class="crayon-line crayon-striped-line"><span class="crayon-h">&nbsp;&nbsp; </span><span class="crayon-st">delay</span><span class="crayon-sy">(</span><span class="crayon-cn">1000</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div>
<div id="crayon-5d4201ed85f15799278526-25" class="crayon-line"><span class="crayon-h">&nbsp;&nbsp; </span><span class="crayon-st">digitalWrite</span><span class="crayon-sy">(</span><span class="crayon-v">valvula</span><span class="crayon-sy">,</span><span class="crayon-k">HIGH</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span> <span class="crayon-c">// desliga v&aacute;lvula</span></div>
<div id="crayon-5d4201ed85f15799278526-26" class="crayon-line crayon-striped-line"><span class="crayon-sy">}</span></div>
<div id="crayon-5d4201ed85f15799278526-27" class="crayon-line">&nbsp;</div>
<div id="crayon-5d4201ed85f15799278526-28" class="crayon-line crayon-striped-line"><span class="crayon-st">else</span><span class="crayon-sy">{</span></div>
<div id="crayon-5d4201ed85f15799278526-29" class="crayon-line"><span class="crayon-c">// se n&atilde;o, interrompe a passagem de &aacute;gua</span></div>
<div id="crayon-5d4201ed85f15799278526-30" class="crayon-line crayon-striped-line"><span class="crayon-h">&nbsp;&nbsp; </span><span class="crayon-st">digitalWrite</span><span class="crayon-sy">(</span><span class="crayon-v">valvula</span><span class="crayon-sy">,</span><span class="crayon-k">HIGH</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div>
<div id="crayon-5d4201ed85f15799278526-31" class="crayon-line"><span class="crayon-h">&nbsp;&nbsp; </span><span class="crayon-st">delay</span><span class="crayon-sy">(</span><span class="crayon-cn">1000</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div>
<div id="crayon-5d4201ed85f15799278526-32" class="crayon-line crayon-striped-line"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-sy">}</span></div>
<div id="crayon-5d4201ed85f15799278526-33" class="crayon-line"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-st">delay</span><span class="crayon-sy">(</span><span class="crayon-cn">3000</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span> <span class="crayon-c">// Aguarda 3s para verificar se solo est&aacute; umido novamente</span></div>
<div id="crayon-5d4201ed85f15799278526-34" class="crayon-line crayon-striped-line"><span class="crayon-sy">}</span></div>
<div class="crayon-line crayon-striped-line">
<p>Se voc&ecirc; desejar que o rel&eacute; fique ativado por mais ou menos tempo, mude o valor dos delay&nbsp;nos comandos&nbsp;<strong>IF</strong>&nbsp;e&nbsp;<strong>ELSE</strong>.</p>
<p>A mangueira foi conectada a uma fonte de &aacute;gua, que pode ser de uma torneira ou um reservat&oacute;rio.&nbsp;Verifique a parte rosqueada da v&aacute;lvula, coloque a mangueira que ser&aacute; utilizada como entrada de fluido. A sa&iacute;da ficar&aacute; pr&oacute;xima ao solo irrigado, seja no vaso ou jardim.</p>
<p>Ajuste os valores no c&oacute;digo conforme a necessidade. Tanto para medir a umidade de solo (no sketch atual, 400), tanto para os delays (de tempo de ativa&ccedil;&atilde;o do rel&eacute; e verifica&ccedil;&atilde;o da umidade).</p>
</div>
<p>&nbsp;</p>

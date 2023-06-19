# TrabalhoViel
Bibliotecas

	O código começa importando algumas bibliotecas, a opneCV no código cv2 que irá permitir a manipulação de imagens feita pelo código, a Numpy que é usada para a manipulação de arrays multidimensionais e por fim a biblioteca matplotib junto a pyplot que não chega a ser usado no código.

Conversão de imagem RGB em imagem Grayscale

	Esse parte do código começa pegando uma imagem e depois a mostrando como teste mas sua verdadeira função é transformar uma imagem colorida em formato RGB para uma imagem Grayscale uma especie de coloração/filtro que consiste na imagem em diferentes tons de cinza. RGB ou Red, Green, Blue (Vermelho, Verde, Azul) é uma das formas de armazenar as cores de uma imagem, nesse código a imagem tem cada uma das três cores separadas criando três arrays diferentes, cada array tem seus valores em cada posição represantando os pixels multiplicado e depois somados entre sí conforme uma fórmula expecífica, no fim formando novamente uma única array com o uso do numpy para criá-la, só que agora em tons de cinza.
	O comando "split(img)", é responsável por dividir a imagem "img" em três imagens separadas, cada uma responsável por uma cor primaria. A variável "img_grayscale_pondered" é criada para armazenar as imagens separadas com valores modificados para tons de cinza. para isso acontecer é utilizada uma fórmula para ponderar os valores de cada canal de cor da imagem. Com o comando "np.array()" e o parâmetro "dtype=np.uint8", é possível converter a imagem em um array de valores inteiros de 8 bits, que representam as cores da imagem em uma faixa de 0 a 255, garantindo que os valores das cores estejam dentro de um intervalo permitido. Por fim, será possível exibir a imagem alterada com a função "cv2_imshow()".

Transformações

	A função “imread()” é capaz de fazer a manipulação de imagens através do OpenCV, é importante lembrar que a variável “colorida” deve ser do tipo booleana e que a função retorna uma imagem em formato de matriz, onde cada elemento representa o valor de um pixel na imagem. A manipulação de cores através da substituição de 255 é uma forma de inverter a escala de cores da imagem. Essa parte permite a escolha de criar uma imagem com cores ou com tons de cinza só que com seus valores invertidos, pela substração do valor da cor pelo seu valor máximo consigo invertes suas cores, por exemplo 255 que é a intensidade máxima no sistema RGB menos 255 é igual a 0 que é o valor mínimo, branco vira preto ou vice versa já que se diminuirmos 0 de 255 ganhamos o valor 255 o inverso de 0.
	 Após essa parte temos mais alterações de imagem através da modificação dos valores RGB da imagem, as variáveis "a" e "b" modificam as cores de uma imagem, a variável "b" aumenta a escala das cores através de uma soma, e a variável "a" multiplica o valor das cores, essas operações podem intensificar ou atenuar as cores, dependendo dos valores de "a" e "b". Para não gerar erro, é utilizada uma função de conversão que  se o resultado ultrapassar o valor máximo ou for menor que o valor mínimo permitido (0 a 255) um ajuste é feito para manter o resultado dentro dos limites.


Filtro Espacial

	A função cv2.filter2D() é utilizada para aplicar uma convolução na imagem utilizando o kernel, kernel é usado para multiplicar toda a imagem, porém a multiplicação não é feita de número em número mas sim alterando o valor de um pixel conforme os valores dos pixels ao seu redor. Kernel faz uma operação de convolução podendo aplicar uma série de efeitos na imagem, como suavização e esse kernel 1/25 que está citado que é utilizado para suavizar a imagem e reduzir o contraste excessivo entre as cores. 

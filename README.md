Código: 


#aplicando conversão básica
#numpy
#img_grayscale_basic = (img[ : , : ,0]+img[ : , : ,1]+img[ : , : ,2])/3

#cv2
B, G, R = cv2.split(img)
img_grayscale_basic = (B+G+R)/3

img_grayscale_basic = np.array(img_grayscale_basic, dtype=np.uint8)
cv2_imshow(img_grayscale_basic)
#cv2.imshow('img_grayscale_basic', img_grayscale_basic)
#cv2.waitKey(0)
#cv2.destroyAllWindows()

Explicação:

O algoritmo tem a função de converter uma imagem RGB (colorida), em uma imagem em escalas de cinza ou “preto e branco” de forma básica.




#img_grayscale_basic = (img[ : , : ,0]+img[ : , : ,1]+img[ : , : ,2])/3

Primeiramente é gerado um vetor com valores de imagem, e eles são divididos de acordo com uma média ponderada que tenta dar ênfase às cores que são enfatizadas pelo olho humano.




#cv2
B, G, R = cv2.split(img)
img_grayscale_basic = (B+G+R)/3

Em seguida, são geradas as variáveis B, G, R. E elas são definidas como as tonalidades azul, verde e vermelho de uma imagem por conta do comando split. Após isso são postos no vetor os valores de B onde era 0, de G onde era 1, e de R onde era 2. Dando por isso mais predominância para a cor vermelha, e menos para a azul. E é gerada a média ponderada entre elas, e essa média passa a ser o valor de cada uma das tonalidades em cada parte da imagem.

Por fim, é dado o comando cv2.imshow e o arquivo da imagem entre parênteses, para que ela seja exibida na tela do usuário. E os waitKey(0) e destroyAllWindows() para que as janelas sejam destruídas caso o usuário aperte alguma tecla.

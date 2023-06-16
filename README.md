# prova2-2023M6T2
Desenvolva um código em Python capaz de utilizar o openCV para a leitura de um vídeo (frame a frame) e, para cada frame, o seu código deve identificar e marcar na imagem os retângulos correspondentes a cada uma das faces encontradas. Ao final do código, um novo vídeo deve ser salvo com as faces identificadas.
Um repositório com exemplos relevantes e o arquivo de vídeo que deve ser utilizado pode ser encontrado em: https://github.com/rmnicola/p2-pratica
# Dependencias:
Python: (https://www.python.org/downloads/) 
OpenCV: pip install opencv-python
haarcascade_frontalface_default.xml: Repositorio OpenCV  -->>> (https://github.com/opencv/opencv/blob/master/data/haarcascades/haarcascade_frontalface_default.xml) 
## Explicação
O código começa importando a biblioteca OpenCV usando a instrução 'import cv2'.
A função 'cv2.VideoCapture' é usada para abrir o arquivo de vídeo 'arsene.mp4' e criar um objeto 'video_capture' que pode ser usado para ler os quadros do vídeo.
A função 'cv2.CascadeClassifier' é usada para carregar um classificador Haar Cascade para detecção facial. Este classificador é armazenado na variável 'face_cascade'.
A função 'cv2.VideoWriter_fourcc' é usada para criar um código de quatro caracteres ('fourcc') que representa o codec de vídeo a ser usado para o vídeo de saída. Nesse caso, o codec 'mp4v' é usado.
A função 'cv2.VideoWriter' é usada para criar um objeto 'VideoWriter' que será usado para gravar o vídeo de saída em um arquivo chamado 'output_video.mp4'. O argumento '30.0' especifica os quadros por segundo do vídeo de saída e o argumento '(int(video_capture.get(3)), int(video_capture.get(4)))' especifica o tamanho do vídeo de saída (que é igual ao tamanho do vídeo de entrada).
O código entra em um loop 'while' que lerá os quadros do vídeo de entrada até que não haja mais quadros restantes.
A função 'video_capture.read()' é usada para ler o próximo quadro do vídeo de entrada. A variável 'ret' é definida como 'True' se um quadro for lido com sucesso e 'False' se não houver mais quadros restantes.
Se um quadro foi lido com sucesso, a função 'cv2.cvtColor' é usada para converter o quadro do espaço de cores BGR para o espaço de cores em tons de cinza. (Ele le melhor quando esta em preto e branco)
A função 'face_cascade.detectMultiScale' é usada para detectar rostos na imagem.
Se um ou mais rostos forem detectados, o loop 'for' desenha um retângulo verde ao redor de cada rosto detectado usando a função 'cv2.rectangle'.
A função 'out.write' é usada para gravar o quadro atual (com os rostos detectados) no arquivo de vídeo de saída.
A função 'cv2.imshow' é usada para exibir o quadro atual (com os rostos detectados) em uma janela chamada 'Vídeo'.
Finalmente, a função 'cv2.waitKey' aguarda o pressionamento de uma tecla. Se a tecla 'q' for pressionada, o loop é encerrado e o programa finalizado.
A função 'video_capture.release()' é usada para liberar o arquivo de vídeo de entrada e a função 'out.release()' é usada para liberar o arquivo de vídeo de saída.
A função 'cv2.destroyAllWindows()' é utilizada para fechar todas as janelas que foram criadas pelo programa.

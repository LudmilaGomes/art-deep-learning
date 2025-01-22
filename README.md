# Projeto de IA - Classificação de Pinturas

- Andamento do projeto
	- dataset: mais de 80.000 imagens de obras de arte; inúmeros artistas de várias épocas e de diferentes gêneros de pintura
	- ideia: utilização de deep learning, uso de Convolutional Neural Network (CNN) para classificação do gênero da pintura
	- dificuldades: modelos em treinamento não alcançaram bons resultados
		- modelos muito simples demoram muito pra aprender e apresentam um teto de aprendizado, não passando de 30% de acurácia sobre o conjunto de validação
		- modelos complexos sofrem overfitting

#

Algumas notas importantes

Diante das dificuldades encontradas, algumas soluções e ideias foram vistas. A seguir, algumas notas explicativas oriundas de pesquisas realizadas sobre os recursos para melhoria dos modelos:

- melhorar dataset
	- realizar downsample
	- escolher menos classes que tenham quantidades de instâncias equilibradas [confere]
- melhorar modelo
	- alterar pesos no modelo (devido às classes terem diferentes quantidades de instâncias)
	- regularização l1 ou l2

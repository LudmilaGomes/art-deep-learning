# Projeto de IA - Classificação de Pinturas

---

## Sobre o projeto 🇧🇷

Com o objetivo de aprender e estudar a área de Visão Computacional e IA, decidi realizar a classificação dos gêneros de pinturas. 

### Sobre o dataset

Utilizou-se o dataset WikiArt, com mais de 80.000 imagens de obras de arte; inúmeros artistas de várias épocas e de diferentes gêneros de pintura.

### Dificuldades

- Foram realizados testes com abordagens diferentes para o modelo de CNN implementado. Modelos muito simples não aprendiam, modelos muito complexos se sobreajustavam aos dados.
- O dataset escolhido tem diversas classes. Os vários gêneros são bastante variados, e em alguns momentos uma classe também apresenta pinturas muito distintas (a citar, Pop Art). Além disso, existe um grande desbalanceamento das instâncias de cada classe (Impressionism com 12847 instâncias e New Realism com 312, por exemplo).

### Sobre as versões

- Versão 1 apresenta a exploração, análise do conjunto de dados e estudos iniciais sobre Visão Computacional e CNNs (Convolutional Neural Networks)
- Versão 2 tem a preparação do dataset (exclusão de instâncias multi-rotuladas; foram mantidas apenas 5 classes do dataset original) e pré-processamento (com data augmentation em tempo de treinamento). Utilizou-se Keras para criação e treinamento do modelo, com uso de early stopping. O modelo implementado `model_5_classes.weights.h5` alcançou acurácia de 69%.
- Para a versão 3, pretendia-se realizar a classificação de mais classes com mantimento de uma boa acurácia. Para tal, foram necessárias mais medidas para a preparação do dataset. Assim, foram tomadas as seguintes medidas de alterações dos dados: retirada de instâncias multi-rotuladas, exclusão de classes com poucas instâncias, união das 4 classes relativas à Renascença em somente uma, exclusão de classes cujos gêneros apresentam pinturas muito variadas e de difícil apreendimento de padrões (como Pop Art e Fauvism do WikiArt). Após isso, foi feito o pré-processamento dos dados, também com uso de data augmentation em tempo de treinamento, mas também realização de Downsample, para equilibrar as quantidades diferentes de instâncias das 13 classes restantes.
	- Tentou-se utilizar a mesma arquitetura usada na Versão 2 do projeto, mas ele era insuficiente e houve underfitting. Assim, o modelo era simples e não conseguia aprender. Após isso, decidiu-se por utilizar a **ResNet18 pré-treinada**. Assim, as camadas convolucionais da ResNet18 já treinada extraem as características das imagens e é necessário apenas realizar o treinamento para as camadas densas do modelo, estas adaptadas ao dataset atual.
 	- Assim, para a nova metodologia indicada, conseguiu-se 69% de acurácia para 13 classes!
  	- **Importante ressaltar que me baseie no [código](https://github.com/hubert10/ResNet18_from_Scratch_using_PyTorch) para uso da ResNet18, bem como seu treinamento e validação!!!**
- Em uma versão futura, pretende-se testar a acurácia para a  **ResNet18 pré-treinada** sobre o dataset com `WeightedRandomSampler`.

- Experiências apreendidas com o projeto: CNNs, Keras, PyTorch e uso de modelos pré-treinados!

---

## About the project 🇺🇸🇬🇧

With the objective of learning more about Computer Vision and Artificial Intelligence, I decided to desenvolve this project, which focuses on classifying paintings.

### About the dataset

The WikiArt Dataset was used. It contains more than 80,000 paintings by many artists from various periods and diverse genres.

### Dificulties

- I performed many tests with different approaches for the implemented CNN model. Simpler models did not learn properly, and more complex models suffered from overfitting.
- The chosen dataset has many classes. The genres vary, and some classes feature very distinct paintings (such as Pop Art). Moreover, there is an imbalance in the number of instances per class (Impressionism has 12,847 instances while New Realism has only 312).

### About the versions

- Version 1: Exploration and analysis of the dataset, along with studies on Computer Vision and CNNs (Convolutional Neural Networks).
- Version 2: Dataset preparation (multi-labeled instances were removed; only 5 classes were used) and pre-processing (data augmentation during training). Keras was used to create and train the model with early stopping. The model `model_5_classes.weights.h5` achieved an accuracy of 0.69.

- For version 3, the aim was to classify more classes while maintaining good accuracy. To achieve this, additional steps were required in dataset preparation. The following data modifications were implemented: removal of multi-labeled instances, exclusion of classes with few instances, merging the four classes related to the Renaissance into one, and exclusion of classes whose genres feature very varied paintings and patterns that are difficult to learn (such as WikiArt’s Pop Art and Fauvism). After that, data preprocessing was performed, using data augmentation during training as well as downsampling to balance the different quantities of instances among the remaining 13 classes.
	- An attempt was made to use the same architecture as in version 2 of the project, but it was insufficient and resulted in underfitting. The model was too simple and couldn’t learn effectively. Subsequently, it was decided to use the pre-trained ResNet18. With this approach, the convolutional layers of the pre-trained ResNet18 extract image features, and only the dense layers, adapted to the current dataset, need to be trained.
	- Thus, with the new methodology, an accuracy of 69% was achieved for 13 classes!
 	- ****It's important to highlight that I based my work on the [code](https://github.com/hubert10/ResNet18_from_Scratch_using_PyTorch) for the use of ResNet18, as well as for its training and validation!!!****

- In a future version, it is planned to test the accuracy of the pre-trained ResNet18 on the dataset using WeightedRandomSampler.
- Lessons learned from the project: CNNs, Keras, PyTorch, and the use of pre-trained models!

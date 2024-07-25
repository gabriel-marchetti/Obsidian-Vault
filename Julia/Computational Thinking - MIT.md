# 1.1 Image as Data and Arrays
 Computational Science is more based on applications on real world problems. That basically means that if you have something that runs faster, but you don't know why, then a Computational Scientist may use it with no real concern. So it tends to be more concerned with real applications.

## Some of the examples
1. Climate changes and design a algorithm for predicting it.
2. Weekly number of infections (pandemics).
3. Stock prize fast enough.
4. Making medical images.
5. Hurricane monitoring.

![[Workflow Example.svg]]
Os processos geralmente tentam simular os padrões encontrados dentro dos "Inputs" para prever comportamentos. Dessa forma podemos generalizar para novas tecnologias como Machine Learning.
Algumas funções foram usadas durante a aula:
O objetivo era trabalhar com imagens... 
```julia
url = "String-da-Imagem";
image_filename = download(url);
image = load(image_filename);
# Agora temos a imagem carregada!
```

----
#### Exercícios
1. Tentar baixar a própria imagem:
2. Tentar mostrar uma imagem dentro do computador.

#### Respostas:
1. Para a primeira basta mudar o "url" da imagem. Deste modo, vou usar uma outra imagem para desenvolver a aula.
2. Para a segunda temos que desvendar...
	Eu usei o esquema de salvar a imagem e pegar o path dela. Desse modo ficamos com:
	```julia
	img_path = "/home/gabriel/codes/julia/MIT_ComputationalThinking/cat.jpeg";
	img      = load(img_path);
	# Imagem Carregada.
	```

#### Obs:
**O comando que usei para ler o path da imagem foi "readlink -f cat.jpeg"**

----

# Tópicos
Podemos criar Sliders de um modo muito fácil dentro do Julia.
```julia
@bind row_i Slider(1:img_height, show_value = true)
```
```julia
@bind col_j Slider(1:img_width, show_value = true)
```

Desse modo teremos dois sliders que nos ajudarão para fazer um dos exercícios...
Além de sliders com valores específicos, conseguimos criar sliders de modo que certos alcances são representados.
```julia
@bind row_range RangeSlider(1:img_height, show_value = true)
@bind col_range RangeSlider(1:img_width, show_value = true)
```

## Processos
Agora que sabemos modificar imagens, podemos começar a falar de processos dentro do Julia. Especificamente em processo de imagens. Podemos primeiro falar da representação de cores, temos um sistema bem conhecido que é o RGB 

# Abstração
Abstração tem o sentido contrário de especialização. Desse modo, a linguagem Julia ajuda muito em alguns tipos de abstração de estruturas de dados. Algumas pessoas dizem que a verdadeira eficiência para programas de computadores é saber onde especializar os códigos e onde abstrair eles. 

# Homework 1

### Note about mutation code
Sabemos que um código sempre tem partes modificadas, desse modo sempre fica a pergunta se é necessário modificar os dados iniciais em prol da otimização do código. Entretanto, nos códigos é preferível manter a integridade dos dados iniciais!
Desse modo, temos uma normalização dos códigos em Julia. Códigos que modificam os dados iniciais são acompanhados de "!" no nome. Assim:
```julia
function sort(list)
	# code
end

function sort!(list)
	# code
end
```

Tem funções diferentes, de modo que o primeiro cria uma cópia da lista e sorteia seus elementos, enquanto a segunda modifica a lista inicial.


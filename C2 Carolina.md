**Questão A - Explique a metodologia para criar a animação em cada um dos casos (versões). Comente-as. Justifique.**

Na versão “gapminder animation” estão presentes as quantidades de anos e o código de cada gráfico. A animação é criada a partir de um ciclo for i in data year.unique(): o que faz com que se crie uma nova imagem. 
O código: filename='Gapminder_step'+str(i)+'.png'
plt.savefig(filename, dpi=96)
plt.gca()  guarda as imagens criadas. O image magick usa essas imagens e vai converte-las numa animação, em gif.
Já na outra versão, “Gapminder_animation-FuncAnimation_PLOT_SEM-legend” a animação é criada pela função def animate(i), sendo i a variável e é nesta que se vai definir a animação. O código plt.title vai definir o título. Esta função por não dar para criar uma imagem diferente para cada ano vai sobrepor todas essas imagens.
E o código ani = animation.FuncAnimation(fig, animate, frames=len(anos), interval=200, blit=False, repeat=False), vai ser o código que dá a animação.O código FuncAnimation faz a passagem entre os anos no gráfico.
O código scut=plt.scatter vai definir como é que as bolhas se vão formar de acordo com a esperança média de vida. A população do país é o tamanho da população. Sempre que o gráfico muda de ano, este muda para o ano correspondente.
**Questão B - Temos “bolhas” de cinco (5) cores diferentes. O que representa cada cor? Justifique, com descrição detalhada do processo.**
Cada uma das cores das bolhas representa continentes diferentes (Europa, Ásia, América, África e Oceânia). O código c=tmp[‘continent’].cat.codes tem como objetivo atribuir a mesma cor às bolhas com a esperança média de vida de todos os países de determinado continente, de acordo com o mapa de cores “Accent” e a opacidade vai ser definida pelo alfa=0.6.
**Questão C - Inserir uma legenda ou legendas com a cor das “bolhas” e o seu significado, posicionada(s) em área(s) que não se sobreponha(m) às “bolhas”. Fundamente as opções tomadas.**
A cada elemento foi adicionada uma legenda com o nome do continente correspondente e de forma a não haverem repetições – daí o uso do código “unique”. Esta ficou com o título de “Continentes” e ficou situada no canto inferior direito de forma a não sobrepor nenhuma das “bolhas” –“loc=4”.


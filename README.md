# Requisicoes-Http-API-
Fazendo requiscoes http com Js puro atraves do Fetch()

* Link do Projeto em produção
<a href="https://apinutriappjlms.netlify.app/">NutriApp</a>

```

let listaElementos = document.querySelector('#app');

let posts = [];

function nutriApp() {
    
    fetch(url) --Acessando a URL para requisicao
    .then((r)=> r.json()) -- transformando a requisicao em json
    .then((json)=> {
        posts = json; -- passando o json para lista vazia


        *** criando os elementos HTML via Javascript para renderizar na tela
        posts.map((item)=> { --usando o .map() para iterar a cada item do meu Array

            let elementoLi = document.createElement('li');
            let tituloElemento = document.createElement('strong');
            let elementoImg = document.createElement('img');
            let elementoDescricao = document.createElement('p');

            let textoTitulo = document.createTextNode(item.titulo);
            tituloElemento.appendChild(textoTitulo)
            elementoLi.appendChild(tituloElemento);

            elementoImg.src = item.capa;
            elementoLi.appendChild(elementoImg);

            let textoSubtitulo = document.createTextNode(item.subtitulo);
            elementoDescricao.appendChild(textoSubtitulo);
            elementoLi.appendChild(elementoDescricao);

            listaElementos.appendChild(elementoLi);

        })


        
    })
    .catch(()=>{
        console.log(`Algo deu Errado`);
    })


    
}

nutriApp();

```

# Requisicoes-Http-API-
Fazendo requiscoes http com Js puro atraves do Fetch()

```

let listaElementos = document.querySelector('#app');

let posts = [];

function nutriApp() {
    
    fetch(url)
    .then((r)=> r.json())
    .then((json)=> {
        posts = json;

        posts.map((item)=> {

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

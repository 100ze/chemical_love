# Chemical Love
Um "adicionador" de classes button. Ele serve como um snippet rápido que eu executo para adicionar manualmente os botões que existem na página mas o [Vimium](https://vimium.github.io/ "Vimium") não consegue reconhecer sozinho

Para adicionar o script nas páginas eu utilizo essa [excelente extensão](https://chrome.google.com/webstore/detail/inject-code/gpaakhhkcmlenabckmapmlfnajboobbi "excelente extensão")

:)



```javascript
/*

  Chemical Love
  v0.1
  
*/

var listas_de_itens = [
  ".list_dados",
  ".menu"
]

var itens = [
  ".r_rumia_icone",
  ".dialog_dados > .corpo"
]

function possui_a_classe_button(elemento){
  return elemento.classList.contains("button")
}

function adicionar_a_classe_button_se_nao_tiver(elemento){
  if(!possui_a_classe_button(elemento)){
    elemento.classList.add("button")
  }
}

function chemical_love(){
  listas_de_itens.forEach((seletor_da_lista) => {
    const lista = document.querySelector(seletor_da_lista)
    
    if(lista){
      for (let i = 0; i < lista.children.length; i++) {
        adicionar_a_classe_button_se_nao_tiver(lista.children[i])
      }  
    }
  })
  
  itens.forEach((seletor_do_item) => {
    const item = document.querySelector(seletor_do_item)
    
    if(item){
      adicionar_a_classe_button_se_nao_tiver(item)      
    }
  })
}

function super_advanced_error_control() {
  try {
    chemical_love()
  } catch (e) {
    console.log("Looka Bomba")
  }
}

//chemical_love()

setInterval(super_advanced_error_control, 500)
```

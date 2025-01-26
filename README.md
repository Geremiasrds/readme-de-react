 # COMPONENTES

### Componente de função.
```
const NomeDaFunção = () => {
    return(
         <div className="nome">
            //tegs jsx.
         </div>
    ) 
}
```
### Componente com class.
```
import React from 'react'

class Nome extends React.Component {
    render() {
         return(
         <div className="nome">
            //tegs jsx.
         </div>
    )
    }
}
```
### Propriedades para os componentes.
As props são utilizadas para enviar dados de um componente pai para um componente filho, permitindo a personalização e reutilização dos componentes.

Dentro do componente pai deve ser ser colocado a prop
```
<Nome title='NomeDaProp'/>

```
Este é ocódigo do componente filho de class.
```

class Nome extends React.Component {
    render() {
         return(
         <div className="nome">
            <h1>{this.props.title}</h1>
            //tegs jsx.
         </div>
    )
    }
}
```
- Este é o código do compenente filho com função

```
const NomeDaFunção = (props) => {
    return(
        <div className="nome">
            <h1>{props.title}</h1>
         </div>
    ) 
}
//Outra forma funcional.
const NomeDaFunção = ({title}) => {
    return(
        <div className="nome">
            <h1>{title}</h1>.
         </div>
    ) 
}
```


##  Prop children.
O prop children permite que você passe componentes, elementos ou até mesmo texto como propriedades para um componente pai no React.
```
const NomeDaFunção = (props) => {
    return(
         <>
            {props.children}
             //tegs jsx.
         </>
    ) 
}
// Agora os cód jsx podem ser criado dentro do componente pai ou filho . 
```

## Propriedades padrão default de componentes.
É uma forma da gente inicializar algumas propriedade do nosso componente com valores padrão quando a gente não quer ou não precisa passar algum valor pra dentro deles.

-  pai deve esta com a propriede exemplo.

```
< NomeDaFunção Label='nomeDaProp' />
```
- Agora a prop que foi colocada no componente pai pode ser usada.

```
const NomeDaFunção = (props) => {
    return(
         <div className="nome">
            <button> {props.label} </button>
            //tegs jsx.
         </div>
    ) 
}

Button.defaultProps = {
    label: 'Clique aqui', ou outras props
}
```
## Sobre Proptypes
Pra ultilizar proptypes deve ser instalado/executado dentro da pasta do projeto react com um dos comando abaixo.
```
npm install prop-types
```
```
yarn install prop-types.
```
#### Como usar proptypes
- Primeiro ele deve ser importado.

```
import PropTypes from 'prop-types'
```
- Criar o código de função.

```
const Nome = ( props )  => {
    return(
        <>
            //Tegs jsx
        </>
    )
}


Count.propTypes = {

}
```

### Como ultilizar multiplos componentes.
- Componente pai.

```
<NomeDoComponente />
```
- Componentes filhos, aqui é onde fica os componentes de cada filho.

```
<NomeDoComponente />
```
- Aqui é onde fica o código do componente filho.

```
const NomeDoComponente = () => {
    return(
        <div>
            //cód jsx
        </div>
    )
}

export default NomeDoComponente
```


### Como criar lista no react
- Primeiro devemos ir em algum componente pai no react e criar com array de string. dentro do array deve esta o nome de cada componente que queremos dentro da lista e cada componete que for participar da lista deve ter o ` key={NomeDaLista} `

. exemplo ``const NomeDaLista = ['nome1', 'nome2', 'nome3']``

- Aqui vai ser feito o código do componente de lista.

```
const NomeDoComponente = () => {
    return(
        <div>
            { NomeDaLista.map((NomeDaLista, index) =>{
                return (
                    <NomeDoComponent key={index}>
                        <H2>{NomeDaLista}</h2>
                        //cód jsx
                    </NomeDoComponent>
                    )
            }) }
        </div>
    )
}
```
### Como criar eventos no react.
- Modelo simples.

```
const Evento = () =>{
    //Aqui deve ser colocado oque queremos que o botão faça
}

const NomeDoComponente = () => {
    return(
        <div>
            <button onClick={sayhello}></button>
            //cód jsx
        </div>
    )
}
```
#### Eventos com props

o componente pai deve esta recebendo o nome color por padrão
```
<CompopnentePai color='nome da cor' >
  //cód jsx
</CompopnentePai>
```

 ```
const nomeDaFunção = () => {
    //Aqui deve ser colocado oque queremos que faça quando clicar
}

  const NomeDaFunção = ({children, color} nomeDaFunção = {nomeDaFunção}) => {
    return(
         < onClick={() => nomeDaFunção(color)}>
            {children}
             //tegs jsx.
         </>
    ) 
}

NomeDaFunção.defaultProps = {
    color: red;
}
  ```
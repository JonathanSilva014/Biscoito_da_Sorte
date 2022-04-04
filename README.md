import React, { Component } from 'react';
import { View, Text, StyleSheet, Image, TouchableOpacity, } from 'react-native';

class App extends Component{

  constructor(props){
    super(props);
    this.state = {
      textoFrase: '',
      img: require('./src/biscoito.png'),
    };

    this.quebrarBiscoito = this.quebrarBiscoito.bind(this);

    this.frases = [
      'Siga os bons e aprender com eles.',
      'Trabalhe e se esforce para não depender dos outros.',
      'O bom-senso vale mais do que muio conhecimento.',
      'O riso é a maior distancia entre duas pessoas.',
      'Deixe de lado as preocupações e seja feliz.',
      'Viva o amor intenso e não de bola para o que os outros vão pensar!',
      'Ame o Proximo',
      'Realize o obvio, pense no improvável e conquiste o impossível',
      'Acredite em milagres, mas não dependa deles.',
      'A maior barreira para o sucesso é o medo do fracasso!',
      'Corra atrás dos seus sonhos, NÃO DESISTA!',
      'O sucesso nasce do querer, da determinação e persistência em se chegar a um objetivo. Mesmo não atingindo o alvo, quem busca e vence obstáculos, no mínimo fará coisas admiráveis.',
      'Lute. Acredite. Conquiste. Perca. Deseje. Espere. Alcance. Invada. Caia. Seja tudo o quiser ser, mas, acima de tudo, seja você sempre.',
      'A coragem não é ausência do medo; é a persistência apesar do medo.',
      'Você é um Trabalhador(a) e sabe o que quer! ENTÃO CONTINUE NA LUTA IRMÃO(A)',
      'Apartir de Agora você é uma nova Pessoa, mais ambiciosa e determinada.',
      'Se o Amor Foi embora, DEIXE IR e se for para ser, ele(a) voltará .',
    ];
  }

  quebrarBiscoito(){
    let numeroAleatorio = Math.floor(Math.random() * this.frases.length);

    this.setState({
      textoFrase: ' "' + this.frases[numeroAleatorio] + '" ',
      img: require('./src/biscoitoAberto.png')
    })
  }

  render(){
    return(
      <View style={styles.container}>

        <Image
        source={this.state.img}
        style={styles.img}
        />

        <Text style={styles.textoFrase}>{this.state.textoFrase}</Text>

        <TouchableOpacity style={styles.botao} onPress={this.quebrarBiscoito}>
          <View style={styles.btnArea}>
            <Text style={styles.btnTexto}>Quebrar Biscoito</Text>
          </View>
        </TouchableOpacity>
      <Text style={styles.jonathan}>Programador Front-End Jr Jonathan Silva</Text>
      </View>
    );
  }
}

const styles = StyleSheet.create({
   container:{
     flex:1,
     backgroundColor: '#2F4F4F',
     paddingTop: 20,
     alignItems: 'center',
     justifyContent: 'center',
   },
   btnTexto:{
    fontSize: 20,
    fontWeight: 'bold',
    color: '#dd7b22',
   },
   img:{
     width: 250,
     height: 250,
   },
   textoFrase:{
    fontSize: 30,
    color: '#dd7b22',
    margin: 30,
    fontStyle: 'italic',
    textAlign: 'center',
   },
   botao:{
    width: 230,
    height: 50,
    borderWidth: 2,
    borderColor: '#dd7b22',
    borderRadius: 25,
  },
  btnArea:{
    flex:1,
    flexDirection: 'row',
    justifyContent: 'center',
    alignItems: 'center',
  },
  jonathan:{
    marginTop:100,
  }

});
export default App;


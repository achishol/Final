import React, {Component} from 'react';
import { StyleSheet, Text, View, Image, Linking, TextInput, Button, ScrollView } from 'react-native';
import {createStackNavigator, createAppContainer, createButtonTabNavigator} from 'react-navigation'
class Final extends Component {
  render() {
    return (
      <View>
        _doIt = () =>{
          this.props.navigation.navigate('Donate')
        }
        <ScrollView>
        <Text style={{ fontSize: '40px', fontWeight: 'bold', textAlign: 'center', textDecorationLine: 'underline'}}>
          Charity +
        </Text>
        <Image
          style={{width: 150, height: 150, alignSelf: 'center'}}
          source={{uri:'https://dpqe0zkrjo0ak.cloudfront.net/img/logos/gg_vertical_color.jpg'}}
        />
        <Button
          title="Sign up"
          onPress={this._GlobalGiving}
          style={StyleSheet.button}
          />
        <Image
          style={{width: 200, height: 160, alignSelf: 'center'}}
          source={{uri:'https://www.wku.edu/leadership_vol/images/stjude_logo.jpg'}}
        />
        <Button
          title="Sign up"
          onPress={this._StJude}
          style={StyleSheet.button}
          />
        <Image
          style={{width: 200, height: 150, alignSelf: 'center'}}
          source={{uri:'https://youngstowngamedevelopers.com/wp-content/uploads/2018/06/extra-life-logo.png'}}
        />
        <Button
          title="Sign up"
          onPress={this._ExtraLife}
          style={StyleSheet.button}
          />
          <Button
          title="Donate on app"
          onPress= {this._doIt}
        />
        </ScrollView>
      </View>
    );
  }
  _GlobalGiving = () => {
    Linking.openURL ('https://www.globalgiving.org/dy/v2/pe/application/start.html')
  }
  _StJude = () => {
    Linking.openURL ('https://www.stjude.org/donate/pm.html?sc_dcm=257564077&sc_cid=kwp75696&source_code=IIQ190721002&msclkid=d727ddf06f2211b762c88364c1164359&utm_source=bing&utm_medium=cpc&utm_campaign=Brand%20%7C%20Donate%20%7C%20Donate&utm_term=%2Bst%20%2Bjude&utm_content=Fundraising')
  }
  _ExtraLife = () => {
    Linking.openURL ('https://www.extra-life.org/index.cfm?fuseaction=cms.page&id=1548')
  }
}

class Donate extends Component {
  render() {
    return (
    <View>
      <TextInput
        style={{borderColor: 'gray', borderWidth: 1}}
        placeholder="Enter $ amount"/> 
      />
      <Button
        title="Submit"
      />
    </View>
    );
  }
}
const AppNavigator = createStackNavigator({
  Final:{
    screen: Final

  },
  Donate:{
    screen: Donate
  },
}, {
  initialRouteName: 'Final'
});

const AppContainer = createAppContainer(AppNavigator);

class App extends Component{
  render(){
    return <AppContainer/>;
  }
}

export default Final;

# Accordion

> Simple drop down item component for react-native. This component supports drop down toggle with animation.<br/>

![image](https://user-images.githubusercontent.com/27461460/47951961-a7a7e500-dfab-11e8-9189-86c0eddb6e12.gif)

## Props

|                      | necessary | types                  | default       |
| -------------------- | --------- | ---------------------- | ------------- |
| contentVisibleOnLoad |           | boolean                | `false`       |
| header               | ✓         | any                    | `<View/>`     |
| backgroundColor      |           | string                 | `transparent` |
| titleBackground      |           | string                 | `transparent` |
| contentBackground    |           | string                 | `transparent` |
| underlineColor       |           | string                 | `transparent` |
| visibleElement       |           | ReactElement           | `null`        |
| invisibleElement     |           | ReactElement           | `null`        |
| style                |           | `StyleProp<ViewStyle>` | `undefined`   |
| children             | ✓         | ReactElement           | `undefined`   |

## Installation

```sh
yarn add @dooboo-ui/core
```

## Getting started

- Import

  ```javascript
  import { Accordion } from '@dooboo-ui/core';
  ```

- Data

  ```javascript
  state = {
    contents: [
      {
        title: 'Title 1',
        body: 'Hi. I love this component. What do you think?',
      },
      {
        title: 'See this one too',
        body: 'Yes. You can have more items.',
      },
      {
        title: 'Thrid thing',
        body:
          'What about very long text? What about very long text? What about very long text? What about very long text? What about very long text? What about very long text? What about very long text? What about very long text? What about very long text? What about very long text? What about very long text? What about very long text?',
      },
    ],
  };
  ```

- Usage
  ```tsx
  <View style={styles.container}>
    <ScrollView style={{ alignSelf: 'stretch' }}>
      {
        this.state.contents
          ? this.state.contents.map((param, i) => {
            return (
              <Accordion
                key={i}
                style={styles.Accordion}
                contentVisible={false}
                visibleElement={
                  <StyledImage
                    source={IC_ARR_UP}
                  />
                }
                invisibleElement={
                  <StyledImage
                    source={IC_ARR_DOWN}
                  />
                }
                header={
                  <View>
                    <Text style={{
                      fontSize: 16,
                      color: 'blue',
                    }}>{param.title}</Text>
                  </View>
                }
              >
                <Text style={[
                  styles.txt,
                  {
                    fontSize: 20,
                  }
                ]}>
                  {param.body}
                </Text>
              </Accordion>
            );
          })
          : null
      }
      <View style={{ height: 96 }}/>
    </ScrollView>
  </View>
  });
  ```

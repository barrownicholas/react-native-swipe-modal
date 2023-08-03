# @birdwingo/react-native-reanimated-graph

## About

`react-native-swipe-modal` is a customizable and animated modal component that can be used in React Native applications. It provides a smooth swipe-to-close functionality along with various configuration options to suit different use cases. It is used in the [Birdwingo mobile app](https://www.birdwingo.com) to show different kinds of popups and explanations.

## Installation

```bash
npm install react-native-reanimated
npm install react-native-gesture-handler
npm install @birdwingo/react-native-swipe-modal
```

**This library provides two modal components. One is AnimatedModal that will animated content when shown. The other is SwipeModal that allows you move with modal**

## SwipeModal

### Usage

To use the `SwipeModal` component, you need to import it in your React Native application and include it in your JSX code. Here's an example of how to use it:

```jsx
import React, { useRef } from 'react';
import { View, Text } from 'react-native';
import SwipeModal, { SwipeModalPublicMethods } from '@birdwingo/react-native-swipe-modal';


const YourComponent = () => {

  const modalRef = useRef<SwipeModalPublicMethods>(null);

  const showModal = () => modalRef.current?.show(); // Call this function to show modal
  const hideModal = () => modalRef.current?.hide(); // Call this function to hide modal

  return (
    <SwipeModal ref={modalRef}>
      <View>
        <Text>Swipe Modal</Text>
      </View>
    </SwipeModal>
  );

};

export default YourComponent;
```

### Props

- `children` (required): The content to be rendered inside the modal.

- `bg` (optional, default: `'black'`): The background color of the modal.

- `showBar` (optional, default: `true`): Set to `true` to display a bar at the top of the modal.

- `barColor` (optional, default: `'white'`): The color of the bar at the top of the modal.

- `maxHeight` (optional, default: `'max'`): The maximum height of the modal. It can be set to `'max'`, `'auto'`, or a specific number. If `auto` maxHeight of modal will the height modal children need.

- `defaultHeight` (optional, default: `maxHeight`): The default height of the modal.

- `fixedHeight` (optional, default: `false`): Set to `true` if you want to maintain a fixed height for the modal. It means that the height of the modal will get back to the initial position after swipe, if modal was not closed.

- `style` (optional): Additional styles to be applied to the modal.

- `closeTrigger` (optional, default: `'swipeDown'`): The trigger to close the modal. It can be set to `'swipeDown'` or `'minHeight'`. `swipeDown` means that modal will close when modal was swiped down by `'closeTriggerValue'`. `'minHeight'` means that modal will close when height of modal is less than `closeTriggerValue`.

- `closeTriggerValue` (optional, default: `10`): The value that triggers the modal to close when using the `closeTrigger`.

- `scrollEnabled` (optional, default: `false`): Set to `true` if you want the modal content to be scrollable.

- `scrollContainerStyle` (optional): Additional styles to be applied to the scrollable container.

- `scrollContainerProps` (optional): Additional props to be passed to the internal ScrollView component.

- `headerComponent` (optional): A custom component to be displayed at the top of the modal. It's placed above scroll content

- `footerComponent` (optional): A custom component to be displayed at the bottom of the modal. It's placed under scroll content

### Public Methods

- `show()`: Call this method to show the modal.
- `hide()`: Call this method to hide the modal.

## AnimatedModal

### Usage

To use the `AnimatedModal` component, you need to import it in your React Native application and include it in your JSX code. Here's an example of how to use it:

```jsx
import React, { useRef } from 'react';
import { View, Text } from 'react-native';
import AnimatedModal, { AnimatedModalPublicMethods } from '@birdwingo/react-native-swipe-modal';


const YourComponent = () => {

  const modalRef = useRef<AnimatedModalPublicMethods>(null);

  const showModal = () => modalRef.current?.show(); // Call this function to show modal
  const hideModal = () => modalRef.current?.hide(); // Call this function to hide modal

  return (
    <AnimatedModal ref={modalRef}>
      <View>
        <Text>Animated Modal</Text>
      </View>
    </AnimatedModal>
  );

};

export default YourComponent;
```

### Props

- `children` (required): The content to be rendered inside the modal.

- `onShow` (optional): A callback function that will be triggered when the modal is shown.

- `onHide` (optional): A callback function that will be triggered when the modal is hidden.

- `closeOnEmptySpace` (optional, default: `true`): Set to `true` to close the modal when the user taps outside the modal's content.

- `closeOnPressBack` (optional, default: `true`): Set to `true` to close the modal when the user presses the back button (Android only).

- `animationDuration` (optional, default: `300`): The duration of the modal's opening and closing animations, in milliseconds.

- `closeSpaceVisibility` (optional, default: `0.6`): A number between 0 and 1, representing the opacity of empty space, that will close the modal if `closeOnEmptySpace` is enabled.

### Public Methods

- `show()`: Call this method to show the modal.
- `hide()`: Call this method to hide the modal.

## Sponsor

**react-native-reanimated-graph** is sponsored by [Birdwingo](https://www.birdwingo.com).\
Download Birdwingo mobile app to see react-native-reanimated-graph in action!
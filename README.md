# SteelEye Assignment

## Q1. : Explain what the simple List component does.

A List component in React does the following -

i. Lists are a group of text or images. They are composed of items containing primary or secondary actions, which are represented by icons and text.

ii. A React component that renders an unordered list of elements is called simple List. A SingleListItem component that can be selected by the user serves as a representation of each item in the list.

iii. The List component accepts a prop called "items", which is an array of objects representing the items to be displayed. Each item object has a "text" property, which is a string representing the text to be displayed for that item.

iv. The List component uses the "useState" and "useEffect" hooks from React to manage the state of the selected item. When an item is clicked, the handleClick function is called, which sets the "selectedIndex" state to the index of the clicked item.

v. Finally, the List component returns an unordered list element that contains multiple SingleListItem components. The "items" prop is mapped over to create one "SingleListItem" component for each item in the list. Each SingleListItem component is passed as props such as "onClickHandler", "text", "index", and "isSelected" based on the corresponding item object.

vi. Additionally, the SingleListItem and WrappedListComponent components are wrapped in the memo function to optimize performance by memoizing the components and avoiding unnecessary re-renders.

## Q2. What problems / warnings are there with code?

Sol:

i. In WrappedListComponent, there is a syntactical error in useState() i.e., `const [setSelectedIndex, selectedIndex] = useState();`  -> `const [selectedIndex, setSelectedIndex] = useState();`

ii. In WrappedSingleListItem component, the onClickHandler should be passed as an arrow function  i.e.,  `onClick={onClickHandler(index)}` -> `onClick={() => onClickHandler(index)}`
 
iii.  
 WrappedListComponent.propTypes = {
          items: PropTypes.array(PropTypes.shapeOf({
            text: PropTypes.string.isRequired,
          })),
        };

 HERE, arrayof should be used instead of array and shape should be used instead of shapeOf

iv. In the WrappedListComponent, before iterating over the items we need to check if "items" has some elements and is not null and then we can iterate using a map.

v. While passing values to the props in SingleListItem Component we need to pass a bool value i.e, `isSelected={selectedIndex}` ->` isSelected={selectedIndex === index}`

# Q3. Please fix, optimize, and/or modify the component as much as you think is necessary.

Sol. The Optimized code has been attached in the List.js component in the src folder
----->steel-eye ----->src -----> List.js

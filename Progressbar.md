# Styling

as most of the progress-bar style is controlled by browser, to style it from scratch we need to disable its default appearance as follow:

```css
.progress-bar-class-name {
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

```

then we can style different part of it with each browsers specific pseudo-elements. 



#### webkit browsers properties:

- ::-webkit-progress-inner-element
  - the outer most part of the progress bar.
- ::-webkit-progress-bar
  - the entire bar of progress element, the portion below the progress indicator, and child of ((::-webkit-progress-inner-element)).
- ::-webkit-progress-value
  - the progress indicator and child of ((::-webkit-progress-bar)).



bellow is an example for webkit browsers:

```css
::-webkit-progress-value {
  border-radius: 20px;
  background-color: #7be6e8;
}

::-webkit-progress-bar {
  border-radius: 20px;
  background: linear-gradient(to right, #168688 0%, #4db3ff 100%);
}

::-webkit-progress-inner-element {
  border-radius: 20px;
}
```



#### moz browsers property:

- ::-webkit-progress-bar
  - the progress indicator.

to set style for the entire bar of progress element, the portion below the progress indicator in moz browsers we can use ((background)), ((border)), and what-ever we want in progress element itself.



bellow is an example moz browsers:

```css
::-moz-progress-bar {
  border-radius: 20px;
  background-color: #7be6e8;
}

progress {
  width: 100%;
  height: 24px;
  background: linear-gradient(to right, #168688 0%, #4db3ff 100%);
  border: none;
  border-radius: 20px;
}
```



bellow is a complete example to support both ((moz)) and ((webkit)) browsers:

```css
progress {
  width: 100%;
  height: 24px;
  background: linear-gradient(to right, #168688 0%, #4db3ff 100%);
  border: none;
  border-radius: 20px;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

::-webkit-progress-value {
  border-radius: 20px;
  background-color: #7be6e8;
}

::-webkit-progress-bar {
  border-radius: 20px;
  background: linear-gradient(to right, #168688 0%, #4db3ff 100%);
}

::-webkit-progress-inner-element {
  border-radius: 20px;
}

::-moz-progress-bar {
  border-radius: 20px;
  background-color: #7be6e8;
}
```



**Caution:** browser specific pseudo-elements are not standard, and may change in future. before using them we need to check if there is any new changes to them or if they have been standardized or not.

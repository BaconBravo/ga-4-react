# GA4React - Google Analytics 4 React

Simple wrapper of ga4 scripts for React:
https://developers.google.com/analytics/devguides/collection/ga4

## Google Analytics 4 React

Example without components

```

const ga4react = new GA4React(
'YOUR GA CODE',
{ /* ga custom config, optional */ },
[ /* additional code, optional */ ],
5000 /* timeout, optional, defaults is 5000 */,
options /* { nonce: ['first-script-is-async','second-script'] } */

});
ga4react.initialize().then((ga4) => {
  ga4.pageview('path')
  ga4.gtag('event','pageview','path') // or your custom gtag event
},(err) => {
  console.error(err)
})

```

---

## Inject GA4React function in props of childrens

Example with custom components 'GA4R'

```
const Test: React.FC<any> = ({ ga4 }) => {
  return <>{ga4 && console.log(ga4)}</>;
};


<GA4R code="YOUR GA CODE">
    <Test></Test>
</GA4R>
```

## RENDER:

console.log results:

`{pageview: ƒ, gtag: ƒ, event: ƒ}`

---

## Components withTracker

path prop value is sended with pageview

```
const Tracker = withTracker(props => <>{JSON.stringify(props)}</>);
...
 <Tracker path="myCustomPath" gaCode="GA-CODE"></Tracker>

```

---

## useGA4React Hook

```
const Example = () => {
  const ga4React = useGA4React(); // GA CODE, optional, if empty try to get from globals
  return <>{JSON.stringify(ga4React)}</>;
};

```

---

<a href="https://www.buymeacoffee.com/unrealmanu" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>

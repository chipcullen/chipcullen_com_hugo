---
title: "How to Fake the Window Object in Jest"
date: 2018-09-19T08:24:00-04:00
draft: true
tags: ["Jest", "Testing"]
---

I was struggling with writing a test the other day for a React component that was mostly a stateless component, but it did read two properties of the `window` object and made some decisions based on that.

The problem is that Jest makes use of `jsdom` which doesn't provide the `window` object. I googled and googled and struggled with many suggestions around problems that weren't _exactly_ what I was trying to solve. Most of the solutions I found were people trying to mock window functions. What I needed was a fake _window object_ itself, and one that didn't involve hacking my `jest.setup.js` file.

A coworker (yet another one who is much smarter than me) suggested that I could solve this by making a lightweight use of **Dependency Injection**. In the context of this article, I'll define that as setting external data points as optional parameters to your function, so that you can _inject_ them in your tests more easily, and you can side-step the vagaries of your test runner.

I will be using React components in this blog post, but there is no reason the concept can't transfer to other JavaScript implementations.

Let's say the component looked something like this:

```javascript
class ourComponent extends Component {
  render() {
    const { data } = this.props;

    const windowData = window.windowData;

    let title = data.title;

    if (windowData) {
      title = windowData;
    }

    return <div className="our-component">{title}</div>;
  }
}

ReactPassportTooltip.propTypes = {
  data: PropTypes.object.isRequired
};

export default ourComponent;
```

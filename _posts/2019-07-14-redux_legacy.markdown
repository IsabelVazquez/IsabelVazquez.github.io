---
layout: post
title:      "Implementing Redux in a Legacy Project"
date:       2019-07-14 09:10:11 +0000
permalink:  redux
tags: redux
---
![Redux Diagram](https://www.filepicker.io/api/file/U6i8YnQTOeNLZYP9uocg)

*Work Reason for introducing Redux with its one source of knowledge:*
Too much bubbling up and down between tightly connected parent and child components with state, props, and callbacks. Performance is hindered and too many components end up relying on the same data that are not necessarily parent-child components. So we had these workarounds to get the data where it needs to be.

*My experience:*
- A lot went into **researching all the services and where their data ended up being use**. Those `axios` calls were eventually moved into Redux-Saga's Generators.  

- **Make sure your code touches every step in the Redux flow.** From having appropriate string constants created, connecting Redux state to the Component in the Container file, and using Redux-Saga to handle asynchronous actions, it was not unusual to find myself going through the various steps, looking for the missing code.

- **Don't be afraid to abstract your code further.** Most of our sagas ended up following a general pattern that a factory could be created for a basic request call. For [example](https://gist.github.com/tricoder42/b8e10ffd1431c6e2691569d6c5a8978d#file-01_fetchsaga-js):
```
export const fetchSaga = (entity, api) => function* ({ payload }) {
    try {
      const data = yield call(api, payload)
      yield put(entity.response(data))
    }
    catch(error) {
      yield put(entity.response(error))
    }
}
```

*Caveat:* State and props work fine for most files but for those files where the same data is constantly being bubbled up/down, Redux is a solution.

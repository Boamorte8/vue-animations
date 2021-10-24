# Vue animations

This project is to learn about animations on Vue

## Learned things

- Vue has the transition tag to help us to animate some elements
- You can rename the default classes to something that you want
- transition doesn't work through components if this has multiples children. The component must has only 1 child
- There is 1 exception when there is a v-if with a v-else
- transition tag has some hooks very useful (beforeEnter, afterEnter, beforeLeave, afterLeave, enter, leave)
- Control animations full with javascript with the hooks added
- Exist the property :css to optimize the animations telling to vue that doesn't search animations on css because the animations is fully controlled by javascript

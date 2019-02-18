# Vuetify nested v-dialog issue

## Setup
```
npm install
npm run serve
```

## Re-produce issue

1. Click delete button on item 1
1. Dialog should say "Delete item with ID 1?"
1. Click delete button on item 2
1. Still OK, dialog should say "Delete item with ID 2?"
1. Click delete button on item 1 again
1. Dialog now says "Delete item with ID 2?"!

## Findings

The dialog HTML containers are layered on top of each other with different z-index.
Clearly, the component fails to identify the correct dialog to show.

Then I realized I could pass parameters to each dialog instance and it solves the issue.

Still I find this a bit awkward and wonder if this works how it's meant to. Perhaps you should get some kind of warning if you use data from the outer context within a nested v-dialog, or at least the docs should warn about this?




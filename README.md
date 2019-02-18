# vuetify-dialog-issue

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Re-produce issue

1. Click delete button on item 1
1. Dialog should say "Delete item with ID 1?"
1. Click delete button on item 1 again
1. Dialog now says "Delete item with ID 2?"
1. Then, continue to click the delete buttons for the rest of the items, and you'll see the pattern...

### Findings

The dialog HTML containers are layered on top of each other with different z-index.
Clearly, the component fails to identify the correct dialog to show.



# drag-drop

A lightweight JavaScript implementation of drag and drop functionality.

## How it works

1. Add `draggable="true"` in HTML for drag items
2. Select draggable items and drop zones
3. Add event listeners for drag events
4. Handle dropping items into zones

## Key Classes

- `.dragging`: Holds the current drag object
- `.drag-over`: For visual feedback on enter and leave

## Events

- `dragstart`, `dragend`: Applied to draggable items
- `dragover`, `dragenter`, `dragleave`: Applied to drop zones
- `drop`: Handles what happens when drop occurs

## Usage

```html
<div class="task" draggable="true">Drag me</div>
<div class="category">Drop here</div>
```

```javascript
// Basic implementation
const tasks = document.querySelectorAll('.task');
const categories = document.querySelectorAll('.category');

tasks.forEach(task => {
  task.addEventListener('dragstart', () => task.classList.add('dragging'));
  task.addEventListener('dragend', () => task.classList.remove('dragging'));
});

categories.forEach(category => {
  category.addEventListener('dragover', e => e.preventDefault());
  category.addEventListener('drop', e => {
    const task = document.querySelector('.dragging');
    category.appendChild(task);
  });
});
```

Customize styles and add more logic as needed for your specific use case.

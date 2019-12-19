# Svelte-File-Upload-Component
This is a pretty simple component that could be used as a web component in non svelte projects. The intent is to marry the input element with drag drop browser functionality. The component itself is slotted and allows for styling.

### Attributes
 * multiple: This indicates if the input event should accept one or many files.
 
### Events
 * input: upon file drop or file selection via the input browse method
 
### Exported Values
 * dragging: boolean - indicates if there is an element being dragged over the component 
 
## Usage
```
<script>
  import FileUpload from 'sveltefileuploadcomponent';
  
  function gotFiles(files) {
    //do something with files
  }
</script>

<FileUpload on:input={gotFile}>
  Whatever you want here.
</FileUpload>
```

## Style
Any elements inside the component will have the parent class "dragging" when an element is being dragged over the file upload component. This allows styling a border or changing some on screen element to indicate a drop is about to occur (or is valid).

The following shows how to change the font color when a drop event is about to occur.

```
<script>
  import FileUpload from 'sveltefileuploadcomponent';
  
  function gotFile(file) {
    //do something with file
  }
</script>

<FileUpload multiple={false} on:input={gotFile}>
  <div class="someClass">Whatever you want here.</div>
</FileUpload>

<style>
  .dragging .someClass{
    color: red;
  }
</style>
```

## Exported Values
A dragging value that is true when a file is being dragged over the element

The following shows how to change the font color when a drop event is about to occur.

```
<script>
  import FileUpload from 'sveltefileuploadcomponent';
  
  function gotFile(file) {
    //do something with file
  }
</script>

<FileUpload let:dragging multiple={false} on:input={gotFile}>
  <div>This is{!dragging ? 'n't' : ''} being dragged over.</div>
</FileUpload>
```

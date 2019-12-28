<script>
    export let note;
    export let updateTitle, updateNote;
</script>

<style>
    .editor {
        display: grid;
        grid-template-rows: 1fr 11fr ;
    }

    input, textarea {
        height: 100%;
        width: 100%;
    }
</style>

<div class="editor">
    <label title="Title input">
        <input autofocus type="text" placeholder="Your title" value="{note.title}" on:input={e => updateTitle(e.target.value)}>
    </label>

    <label>
        <textarea title="Note input" name="note" value="{note.note}" on:input={e => updateNote(e.target.value)} ></textarea>
    </label>
</div>
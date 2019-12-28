<script>
    export let note;
    import marked from 'marked';
</script>

<div class="view">
    <h1>{note.title}</h1>
    {@html marked(note.note)}
</div>
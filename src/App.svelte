<script>
    import Editor from './components/Editor.svelte'
    import Sidebar from './components/Sidebar.svelte'
    import View from './components/View.svelte'

    export let notes = [
        {
            title: 'First',
            note: 'Some contents for the note',
            id: 0
        },
        {
            title: 'Second',
            note: 'Some contents for the note',
            id: 1
        },
        {
            title: 'Third',
            note: 'Some contents for the note',
            id: 2
        },
    ];

    const INITIAL_STATE = {
        title: '',
        note: '',
        id: notes.length
    };

    export let currentNote = INITIAL_STATE;

    export const handleClick = id => currentNote = notes.find(note => note.id === id);
    export const updateTitle = title => currentNote.title = title;
    export const updateNote = note => currentNote.note = note;
    export const createNew = () => currentNote = INITIAL_STATE;

</script>

<style>
    main {
        display: grid;
        grid-template-columns: 2fr 6fr 6fr;
        grid-column-gap: 10px;
    }
</style>

<main>
    <Sidebar {notes} {handleClick} {createNew}/>
    <Editor note="{currentNote}" {updateTitle} {updateNote}/>
    <View note="{currentNote}" />
</main>

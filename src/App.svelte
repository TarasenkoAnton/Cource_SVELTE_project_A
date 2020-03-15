<script>
    import Header from  './UI/Header.svelte';
    import MeetupGrid from './Meetups/MeetupGrid.svelte';
 
let title = '';
let subtitle = '';
let address = '';
let email = '';
let description = '';


const meetups = [
    {
        id: 'm1',
        title: 'Coding deep learning',
        subtitle: 'Learn per 2 hours',
        description:'In this programms we has updates some...',
        imageUrl:'https://upload.wikimedia.org/wikipedia/ru/thumb/8/8b/Rosenblatt.jpg/330px-Rosenblatt.jpg',
        address:'Ukraine, Some where',
        contactEmail:'test@test.ua'

    },
      {
        id: 'm2',
        title: 'Get searching work',
        subtitle: 'Together quik',
        description:'This is dont hardly for you',
        imageUrl:'https://upload.wikimedia.org/wikipedia/ru/thumb/d/de/Neuro.PNG/600px-Neuro.PNG',
        address:'Ukraine, Some where dot 2',
        contactEmail:'testwork@test.ua'

    }
];

function addMeetup (){};
</script>

<style>
main{
    margin-top: 5rem;
}
</style>

<Header/>

<main>
    <form on:submit|preventDefault="{addMeetup}">
        <div class="form-control">
            <label for="title">Title</label>
            <input type="text" id="title">
        </div>
        <div class="form-control">
            <label for="subtitle">Subtitle</label>
            <input type="text" id="subbtitle">
        </div>
        <div class="form-control">
            <label for="address">Address</label>
            <input type="text" id="sddress">
        </div>
        <div class="form-control">
            <label for="imageUrl">Image URL</label>
            <input type="text" id="imageUrl">
        </div>
        <div class="form-control">
            <label for="email">E-Mail</label>
            <input type="email" id="imail">
        </div>
        <div class="form-control">
            <label for="description">Description</label>
            <textarea rows="3" id="description"/>
        </div>
        <button type="submit">Save</button>
    </form>
 <MeetupGrid {meetups} />
</main>


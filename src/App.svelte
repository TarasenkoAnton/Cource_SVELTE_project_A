<script>
    import Header from  './UI/Header.svelte';
    import MeetupGrid from './Meetups/MeetupGrid.svelte';
 
let title = '';
let subtitle = '';
let address = '';
let imageUrl = '';
let email = '';
let description = '';


let meetups = [
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

function addMeetup (){
    const newMeetup = {
            id: Math.random().toString(),
            title: title,
            subtitle: subtitle,
            address: address,
            imageUrl: imageUrl,
            contactEmail: email,
            description: description,
     };

     // meetups.push(newMeetup); // This is DOS'NT works //
     meetups = [newMeetup, ...meetups];
};
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
            <input type="text" id="title" bind:value={title}>
        </div>
        <div class="form-control">
            <label for="subtitle">Subtitle</label>
            <input type="text" id="subbtitle" bind:value={subtitle}>
        </div>
        <div class="form-control">
            <label for="address">Address</label>
            <input type="text" id="sddress" bind:value={address}>
        </div>
        <div class="form-control">
            <label for="imageUrl">Image URL</label>
            <input type="text" id="imageUrl" bind:value={imageUrl}>
        </div>
        <div class="form-control">
            <label for="email">E-Mail</label>
            <input type="email" id="imail" bind:value={email}>
        </div>
        <div class="form-control">
            <label for="description">Description</label>
            <textarea rows="3" id="description" bind:value={description}/>
        </div>
        <button type="submit">Save</button>
    </form>
 <MeetupGrid {meetups} />
</main>


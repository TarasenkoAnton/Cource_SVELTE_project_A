<script>
    import Header from  './UI/Header.svelte';
    import MeetupGrid from './Meetups/MeetupGrid.svelte';
    import TextInput from './UI/TextInput.svelte';
    import Button from './UI/Button.svelte';
 
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
form{
    width: 30rem;
    max-width:90%;
     margin: auto;
}
</style>

<Header/>

<main>
    <form on:submit|preventDefault="{addMeetup}">
<TextInput 
        id="title"
        label="Title"
        value={title}
        type="text"
        on:input={event => (title = event.target.value)}
        />
<TextInput 
        id="subtitl"
        label="Subtitle"
        value={subtitle}
        type="text"
        on:input={event => (subtitle = event.target.value)}
        /> 
<TextInput 
        id="address"
        label="Address"
        value={address}
        type="text"
        on:input={event => (address = event.target.value)}
        />
<TextInput 
        id="imageUrl"
        label="Image UGR"
        value={imageUrl}
        type="text"
        on:input={event => (imageUrl = event.target.value)}
/>
<TextInput 
        id="email"
        label="E-Mail"
        value={email}
        type="email"
        on:input={event => (email = event.target.value)}
/>
<TextInput 
        id="description"
        label="Description"
        value={description}
        controlType="textarea"
        on:input={event => (description = event.target.value)}
        /> 
        <Button type="submit" caption="Save"/>
    </form>
 <MeetupGrid {meetups} />
</main>


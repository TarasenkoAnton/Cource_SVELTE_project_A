<script>
    import Header from  './UI/Header.svelte';
    import MeetupItem from './Meetups/MeetupItem.svelte';
    import SubmeetInfoTabs from './Submeet/SubmeetInfoTabs.svelte';

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
</script>

<style>
#meetups {
    margin-top: 5rem;
}
</style>

<Header/>
<section id="meetups">
{#each meetups as meetup}
    <MeetupItem 
    title={meetup.title},
    subtitle={meetup.subtitle}, 
    imageUrl={meetup.imageUrl}, 
    description={meetup.description},
    address={meetup.address},
    email={meetup.contactEmail}
    />
{/each}
</section>
<SubmeetInfoTabs/>


<script>
    import Header from  './UI/Header.svelte';
    import MeetupItem from './Meetups/MeetupItem.svelte';

const meetups = [
    {
        id: 'm1',
        title: 'Coding deep learning',
        subtitle: 'Learn per 2 hours',
        description:'In this programms we has updates some...',
        imageUrl:'',
        address:'Ukraine, Some where',
        contactEmail:'test@test.ua'

    },
      {
        id: 'm2',
        title: 'Get searching work',
        subtitle: 'Together quik',
        description:'This is dont hardly for you',
        imageUrl:'',
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
    <MeetupItem/>
{/each}
</section>


<template>
    <div>
        <p class="text-2xl italic">Your BIGTALK Topic: </p>
        <p class="text-5xl">{{ topic }}</p>
    </div>
</template>

<script>
    export default {
        name: "Topic",

        data: function () {
            return {
                topics: [],
            }
        },

        mounted () {
            this.topics = [
                "Affirmative Action",
                "Alternative medicine",
                "America's global influence",
                "Artificial intelligence",
                "Assisted suicide",
                "Atheism",
                "Bilingual education",
                "Biofuels",
                "Bitcoins",
                "Capital punishment",
                "Censorship",
                "Charter schools",
                "Childhood obesity",
                "Civil rights",
                "Climate change",
                "Cyber bullying",
                "Drug legalization",
                "Eating disorders",
                "Extremism",
                "Factory farming",
                "Foreign aid",
                "Fracking",
                "Freedom of speech",
                "Genetic engineering",
                "Hacking",
                "Health insurance",
                "Identity theft",
                "Immigration",
                "Labor unions",
                "Minimum wage",
                "Nuclear energy",
                "Organic food",
                "Offshore drilling",
                "Outsourcing",
                "Polygamy",
                "Privacy",
                "Racial profiling",
                "School uniforms",
                "Self-driving cars",
                "Sex education",
                "Social security",
                "Standardized testing",
                "Stem cells",
                "Sweatshops",
                "Title IX",
                "Urban agriculture",
                "Vaccines",
                "Violence in the media",
                "Women's rights",
                "Zero tolerance policies",
            ]
        },

        computed: {
            topic: function () {
                return this.topics[Math.floor(Math.random()*this.topics.length)];
            }
        },
    }
</script>

<style scoped>

</style>

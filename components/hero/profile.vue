<template>
    <section class="section-container">
        <div class="section-box hero-basics">
            <div class="hero-stats columns">
                <div class="column is-full hero-stats-base">
                    <h1>{{ $t("heroes.profile") }}</h1>
                    <hr />
                    <ul>
                        <li v-if="rarity" class="columns is-mobile">
                            <div class="column is-half hero-stats-type">{{ $t("heroes.grade") }}</div>
                            <div :class="`star-rating-${rarity}`" class="column is-half hero-stats-value"></div>
                        </li>
                        <li v-if="role" class="columns is-mobile">
                            <div class="column is-half hero-stats-type">{{ $t("heroes.classType") }}</div>
                            <div :class="`hero-class-${role}`" class="column is-half hero-stats-value no-text">
                                {{ $t(`classes.${role}`) }}
                            </div>
                        </li>
                        <li v-if="element" class="columns is-mobile">
                            <div class="column is-half hero-stats-type">{{ $t("filters.element") }}</div>
                            <div :class="`hero-element-${element}`" class="column is-half hero-stats-value no-text">
                                {{ $t(`elements.${element}`) }}
                            </div>
                        </li>
                        <li v-if="zodiac" class="columns is-mobile">
                            <div class="column is-half hero-stats-type">{{ $t("filters.zodiac") }}</div>
                            <div :class="`hero-sign-${zodiac}`" class="column is-half hero-stats-value no-text">
                                {{ $t(`zodiacSigns.${zodiac}`) }}
                            </div>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    props: {
        rarity: {
            type: Number,
            default: 1,
        },
        zodiac: {
            type: String,
            default: "",
        },
        element: {
            type: String,
            default: "",
        },
        role: {
            type: String,
            default: "",
        },
    },
};
</script>

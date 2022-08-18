<template>
    <div>
  <p class="text-dark">THIS IS THE PROFILE PAGE</p>
    </div>
</template>


<script>
import { onMounted } from 'vue';
import { useRoute } from 'vue-router';
import { logger } from '../utils/Logger.js';
import { profilesService } from '../services/ProfilesService.js';
import Pop from '../utils/Pop.js';

export default {
    setup() {
        const route = useRoute()

        async function getProfileById() {
            try {
                await profilesService.getProfileById(route.params.profileId)
            } catch (error) {
                logger.error("[getProfileById]", error)
                Pop.error(error)
            }
        }

        onMounted(() => {
            getProfileById()
        })
        return {};
    },
};
</script>


<style lang="scss" scoped>
</style>
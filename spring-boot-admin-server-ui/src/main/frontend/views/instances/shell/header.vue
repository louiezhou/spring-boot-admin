<!--
  - Copyright 2014-2018 the original author or authors.
  -
  - Licensed under the Apache License, Version 2.0 (the "License");
  - you may not use this file except in compliance with the License.
  - You may obtain a copy of the License at
  -
  -     http://www.apache.org/licenses/LICENSE-2.0
  -
  - Unless required by applicable law or agreed to in writing, software
  - distributed under the License is distributed on an "AS IS" BASIS,
  - WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  - See the License for the specific language governing permissions and
  - limitations under the License.
  -->

<template>
    <section class="hero is-primary instance-header" id="instance-menu">
        <div class="hero-body">
            <div class="container">
                <div class="columns">
                    <div class="column is-narrow">
                        <h1 class="title" v-if="instance" v-text="instance.registration.name"></h1>
                        <h2 class="subtitle" v-if="instance" v-text="instance.id"></h2>
                    </div>
                    <div class="column">
                        <sba-status v-if="instance" :status="instance.statusInfo.status"
                                    :date="instance.statusTimestamp"></sba-status>
                    </div>
                    <div class="column is-narrow is-hidden-mobile">
                        <h2 class="subtitle is-6" v-if="instance">
                            <a v-text="instance.registration.serviceUrl"
                               :href="instance.registration.serviceUrl"></a><br>
                            <a v-text="instance.registration.managementUrl"
                               :href="instance.registration.managementUrl"></a><br>
                            <a v-text="instance.registration.healthUrl"
                               :href="instance.registration.healthUrl"></a>
                        </h2>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
  export default {
    props: ['instance']
  }
</script>
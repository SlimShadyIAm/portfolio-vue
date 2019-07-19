<template>
    <div class="container">
        <br>
        <div class="tile is-ancestor">
            <div class="tile is-vertical is-8">
                <div class="tile">
                    <div class="tile is-parent is-vertical">
                        <article class="tile is-child notification is-primary">
                            <p class="title">19 Years Old</p>
                            <!-- <p class="subtitle">Top tile</p> -->
                        </article>
                        <article class="tile is-child notification is-warning">
                            <p class="title">Pakistani born</p>
                            <p class="subtitle"></p>
                        </article>
                    </div>
                    <div class="tile is-parent">
                        <article class="tile is-child notification is-info">
                            <p class="title">Middle tile</p>
                            <p class="subtitle">Something here probably</p>
                            
                        </article>
                    </div>
                </div>
                <div class="tile is-parent">
                    <article class="tile is-child notification is-danger">
                        <p class="title">Computer Science Student</p>
                        <p class="subtitle">Second-year Bachelors' program at the University of Twente</p>
                        <div class="content">
                            <!-- Content -->
                        </div>
                    </article>
                </div>
            </div>
            <div class="tile is-parent">
                <article class="tile is-child notification is-success">
                    <div class="content">
                        <p class="title">Areas of expertise</p>
                        <p class="subtitle"></p>
                        <div class="content">
                           <ul class="is-family-primary is-size-5">
                               <li>Frontend design, UI/UX</li>
                               <li>Vue JS, React, Angular</li>
                           </ul>
                        </div>
                    </div>
                </article>
            </div>
        </div>
    </div>
</template>

<style scoped>
    * {
        text-align: center;
    }
    .is-child  {
        padding: 40px;
    }

    ul li {
        text-align: left;
    }
</style>
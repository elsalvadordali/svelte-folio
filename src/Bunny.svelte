

<div class="line bottom">
    <h4 class='title'><a href='https://bunnymoney.app/' target="_new">Bunny Money</a></h4>
    <h4>A Progressive Web App that teaches kids financial literacy, 
        created in svelte.js, typescript. Firebase auth for authentication,
         and firestore for storage.</h4>
</div>


<style>
    .line {
        display: flex;
        flex-flow: row nowrap;
        justify-content: space-evenly;
        
    }
    h4 {
        margin: 0;
        padding: 1vw;
        font-size: 2vw;
        font-family: monospace;
        font-weight: 100;
    }
    .title {
        border-right: 2px solid #8cd3db;
        font-size: 5vw;
        width: 25%;
        padding: 2vw .5vw;
        font-family: 'Bebas Neue', cursive;
        font-weight: 400;
    }
    a:hover, a:focus {
        font-style: italic;
        background-color: #fe676e;
    }
    @media (orientation: portrait) {
        h4 {
            font-size: 1.75vh;
        }
        .title {
            font-size: 4vh;
        }
    }
</style>
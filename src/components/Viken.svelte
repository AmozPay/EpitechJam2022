<script lang=ts>
    export let text: string;
</script>

<figure class="sadken">
    <img src="sadken.png" alt="Sad Viken"/>
    <figcaption class="sadken-text">{text}</figcaption>
</figure>

<style>

.sadken {
    position: absolute;
    padding: 0;
    margin: 0;
    bottom: 0px;
    left: 0px;
}

.sadken img {
    display: block;
    height: 100%;
}

.sadken figcaption {
    display: block;
    position: absolute;
    width: 40%;
    color: black;
    left: 52%;
    top: 20%;
    padding: 0em;
    font-weight: 700;
    font-size: 3vh;
    z-index: 2;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
}
</style>
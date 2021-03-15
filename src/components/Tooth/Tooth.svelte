<script>
    import ToothSide from './ToothSide.svelte'

    export let label;
</script>

<div class="tooth-wrapper">
    <span class="tooth-label">{label}</span>
    <div class="tooth">
        <svg class="tooth-borders" width="48.71px" height="48.71px" viewBox="0 0 48.71 48.71">
            <style type="text/css">
                
            </style>
            <path class="tooth-border" d="M0.35,0.35l15.12,15.12c0.56,0.56,0.88,1.33,0.88,2.12v13.51c0,0.8-0.32,1.56-0.88,2.12L0.35,48.35"/>
            <path class="tooth-border" d="M29.35,32.35h-10c-1.66,0-3-1.34-3-3v-10c0-1.66,1.34-3,3-3h10c1.66,0,3,1.34,3,3v10 C32.35,31.01,31.01,32.35,29.35,32.35z"/>
            <path class="tooth-border" d="M48.35,0.35L33.23,15.47c-0.56,0.56-1.33,0.88-2.12,0.88H17.6c-0.8,0-1.56-0.32-2.12-0.88L0.35,0.35"/>
            <path class="tooth-border" d="M48.35,48.35L33.23,33.23c-0.56-0.56-0.88-1.33-0.88-2.12V17.6c0-0.8,0.32-1.56,0.88-2.12L48.35,0.35"/>
            <path class="tooth-border" d="M0.35,48.35l15.12-15.12c0.56-0.56,1.33-0.88,2.12-0.88h13.51c0.8,0,1.56,0.32,2.12,0.88l15.12,15.12"/>
        </svg>
        <ToothSide top />
        <ToothSide right />
        <ToothSide core />
        <ToothSide bottom />
        <ToothSide left />
    </div>
</div>

<style lang="scss">
.tooth-wrapper {
    display: grid;
    grid-gap: 0.25rem;
}

.tooth {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    grid-template-rows: repeat(6, 1fr);
    position: relative;
    width: 48px;
    height: 48px;
    border-radius: 4px;
    overflow: hidden;
}

.tooth-borders {
    position: absolute;
    left: 0;
    top: 0;
    z-index: 1;
    display: block;
    pointer-events: none;
}

.tooth-border{
    fill: none;
    stroke: #FFFFFF;
    stroke-linejoin: bevel;
    stroke-miterlimit: 10;
    stroke-width: 1;
}
</style>
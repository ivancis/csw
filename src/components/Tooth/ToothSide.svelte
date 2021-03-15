<script>
    export let checked;
    export let top;
    export let right;
    export let core;
    export let bottom;
    export let left;
</script>

<div
    class="tooth-side"
    class:tooth-side--top={top}
    class:tooth-side--right={right}
    class:tooth-side--core={core}
    class:tooth-side--bottom={bottom}
    class:tooth-side--left={left}
    class:is-checked={checked}>
    <input
        class="tooth-checkbox"
        type="checkbox"
        bind:checked={checked}
    />
</div>

<style lang="scss">
$_tooth-side-bg: red;
$tooth-side-bg: var(--tooth-side-bg, #{$_tooth-side-bg});

.tooth-side {
    position: relative;
    transition: all 0.1s ease;

    &--top {
        grid-area: 1 / -1 / 3 / 1;
        border-top: 16px solid $tooth-side-bg;
        border-right: 16px solid transparent;
        border-left: 16px solid transparent;

        .tooth-checkbox {
            width: 48px;
            height: 16px;
            margin: -16px;
        }
    }

    &--right {
        grid-area: 1 / -1 / -1 / -3;
        border-right: 16px solid $tooth-side-bg;
        border-top: 16px solid transparent;
        border-bottom: 16px solid transparent;

        .tooth-checkbox {
            width: 16px;
            height: 48px;
            margin: -16px 0 0;
        }
    }

    &--core {
        grid-area: 3 / -3 / -3 / -5;
        background: $tooth-side-bg;
    }

    &--bottom {
        grid-area: -1 / -1 / -3 / 1;
        border-bottom: 16px solid $tooth-side-bg;
        border-right: 16px solid transparent;
        border-left: 16px solid transparent;

        .tooth-checkbox {
            width: 48px;
            height: 16px;
            margin: 0 -16px;
        }
    }

    &--left {
        grid-area: 1 / 3 / -1 / 1;
        border-left: 16px solid $tooth-side-bg;
        border-top: 16px solid transparent;
        border-bottom: 16px solid transparent;

        .tooth-checkbox {
            width: 16px;
            height: 48px;
            margin: -16px;
        }
    }

    &.is-checked {
        --tooth-side-bg: blue;
    }

    &:hover {
        --tooth-side-bg: darkred;
    }
}

.tooth-checkbox {
    position: absolute;
    left: 0;
    top: 0;
    margin: 0;
    width: 100%;
    height: 100%;
    opacity: .1;
    cursor: pointer;
}
</style>
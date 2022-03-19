// Header.vue

<template>
    <div class="topbar">
        <p class="tagline">
            <img class="tagline__logo" src="../assets/nerp.svg" alt="Logo Nerp">
            <span class="tagline__title">LOU</span>
        </p>
        <!--
        <div id="nav">
            <router-link to="/">Home</router-link> •
            <router-link to="/games">Games</router-link>
        </div>
        -->
        <div>
            <p class="glitch" data-scroll="in">CSS is Awesome</p>
            <p class="reveal--2 words chars splitting" aria-hidden="true" data-scroll="in" data-splitting="" style="--word-total:4; --char-total:17;">
                <span class="word" data-word="Your" style="--word-index:0;">
                    <span class="char" data-char="C" style="--char-index:0; --count:1; --char-0:&quot;≥&quot;; --char-1:&quot;¶&quot;; --char-2:&quot;/&quot;; --char-3:&quot;˚&quot;; --char-4:&quot;░&quot;; --char-5:&quot;≤&quot;; --char-6:&quot;¢&quot;; --char-7:&quot;•&quot;; --char-8:&quot;≥&quot;; --char-9:&quot;˚&quot;;">C</span>
                    <span class="char" data-char="S" style="--char-index:1; --count:3; --char-0:&quot;<&quot;; --char-1:&quot;…&quot;; --char-2:&quot;–&quot;; --char-3:&quot;`&quot;; --char-4:&quot;¶&quot;; --char-5:&quot;ƒ&quot;; --char-6:&quot;•&quot;; --char-7:&quot;?&quot;; --char-8:&quot;˜&quot;; --char-9:&quot;˜&quot;;">S</span>
                    <span class="char" data-char="S" style="--char-index:2; --count:1; --char-0:&quot;░&quot;; --char-1:&quot;æ&quot;; --char-2:&quot;≥&quot;; --char-3:&quot;å&quot;; --char-4:&quot;÷&quot;; --char-5:&quot;–&quot;; --char-6:&quot;∫&quot;; --char-7:&quot;µ&quot;; --char-8:&quot;å&quot;; --char-9:&quot;▒&quot;;">S</span>
                </span>
                <span class="whitespace"> </span>
                <span class="word" data-word="world" style="--word-index:1;">
                    <span class="char" data-char="i" style="--char-index:4; --count:4; --char-0:&quot;?&quot;; --char-1:&quot;™&quot;; --char-2:&quot;–&quot;; --char-3:&quot;/&quot;; --char-4:&quot;˚&quot;; --char-5:&quot;▒&quot;; --char-6:&quot;˜&quot;; --char-7:&quot;?&quot;; --char-8:&quot;░&quot;; --char-9:&quot;÷&quot;;">i</span>
                    <span class="char" data-char="s" style="--char-index:5; --count:4; --char-0:&quot;∆&quot;; --char-1:&quot;§&quot;; --char-2:&quot;ç&quot;; --char-3:&quot;∫&quot;; --char-4:&quot;µ&quot;; --char-5:&quot;™&quot;; --char-6:&quot;`&quot;; --char-7:&quot;§&quot;; --char-8:&quot;˙&quot;; --char-9:&quot;▓&quot;;">s</span>
                </span>
                <span class="whitespace"> </span>
                <span class="word" data-word="of" style="--word-index:2;">
                    <span class="char" data-char="a" style="--char-index:9; --count:3; --char-0:&quot;¶&quot;; --char-1:&quot;ç&quot;; --char-2:&quot;>&quot;; --char-3:&quot;å&quot;; --char-4:&quot;¬&quot;; --char-5:&quot;≤&quot;; --char-6:&quot;∞&quot;; --char-7:&quot;≥&quot;; --char-8:&quot;˚&quot;; --char-9:&quot;>&quot;;">a</span>
                    <span class="char" data-char="w" style="--char-index:10; --count:4; --char-0:&quot;ª&quot;; --char-1:&quot;™&quot;; --char-2:&quot;`&quot;; --char-3:&quot;…&quot;; --char-4:&quot;<&quot;; --char-5:&quot;√&quot;; --char-6:&quot;≥&quot;; --char-7:&quot;≠&quot;; --char-8:&quot;÷&quot;; --char-9:&quot;å&quot;;">w</span>
                    <span class="char" data-char="e" style="--char-index:11; --count:3; --char-0:&quot;≈&quot;; --char-1:&quot;æ&quot;; --char-2:&quot;¬&quot;; --char-3:&quot;å&quot;; --char-4:&quot;¡&quot;; --char-5:&quot;▓&quot;; --char-6:&quot;÷&quot;; --char-7:&quot;≥&quot;; --char-8:&quot;░&quot;; --char-9:&quot;≈&quot;;">e</span>
                    <span class="char" data-char="s" style="--char-index:12; --count:3; --char-0:&quot;>&quot;; --char-1:&quot;™&quot;; --char-2:&quot;∂&quot;; --char-3:&quot;∫&quot;; --char-4:&quot;æ&quot;; --char-5:&quot;░&quot;; --char-6:&quot;§&quot;; --char-7:&quot;•&quot;; --char-8:&quot;©&quot;; --char-9:&quot;©&quot;;">s</span>
                    <span class="char" data-char="o" style="--char-index:13; --count:5; --char-0:&quot;µ&quot;; --char-1:&quot;µ&quot;; --char-2:&quot;√&quot;; --char-3:&quot;º&quot;; --char-4:&quot;<&quot;; --char-5:&quot;ƒ&quot;; --char-6:&quot;∆&quot;; --char-7:&quot;™&quot;; --char-8:&quot;÷&quot;; --char-9:&quot;å&quot;;">o</span>
                    <span class="char" data-char="m" style="--char-index:14; --count:2; --char-0:&quot;∞&quot;; --char-1:&quot;ç&quot;; --char-2:&quot;▓&quot;; --char-3:&quot;˚&quot;; --char-4:&quot;?&quot;; --char-5:&quot;∂&quot;; --char-6:&quot;/&quot;; --char-7:&quot;`&quot;; --char-8:&quot;£&quot;; --char-9:&quot;ß&quot;;">m</span>
                    <span class="char" data-char="e" style="--char-index:15; --count:5; --char-0:&quot;≠&quot;; --char-1:&quot;▒&quot;; --char-2:&quot;∫&quot;; --char-3:&quot;§&quot;; --char-4:&quot;∂&quot;; --char-5:&quot;©&quot;; --char-6:&quot;˙&quot;; --char-7:&quot;░&quot;; --char-8:&quot;<&quot;; --char-9:&quot;>&quot;;">e</span>
                </span>
            </p>
        </div>
    </div>
</template>

<script>

</script>

<style>

    .topbar {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 12px 24px;
        margin: 0 0 24px 0;
        color: hsl(0, 0%, 10%);
        background-color: #FFF;
    }
    .topbar a {
        color: hsl(0, 0%, 10%);
        text-decoration: none;
        margin: 0 10px;
    }
    .tagline {
        display: flex;
        align-items: center;
        margin: 0;
    }
    .tagline__logo {
        display: inline-block;
        width: 30px;
    }
    .tagline__title {
        position: relative;
        letter-spacing: 2px;
        font-weight: 300;
        font-size: 1.0rem;
        margin-left: 14px;
        padding-left: 8px;
        color: hsl(0, 0%, 10%);
    }
    .tagline__title::before {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0;
        display: block;
        width: 6px;
        height: 1px;
        background-color: hsl(0, 0%, 10%);
        margin: auto;
        transform: translateX(-100%);
    }
    p[data-scroll='in'] {
        margin: 0;
    }
    p[data-scroll='in'] [data-char]:after {
        -webkit-animation-name: glitch-switch;
        animation-name: glitch-switch;
    }
    .reveal--2 [data-char]:after {
        -webkit-animation-iteration-count: var(--count);
        animation-iteration-count: var(--count);
    }
    p.glitch {
        position: absolute;
        opacity: 0;
    }
    .word {
        position: relative;
        display: inline-block;
    }
    .whitespace {
        display: inline-block;
        width: 3px;
    }
    [data-char] {
        position: relative;
        display: inline-block;
        color: transparent;
    }
    [data-char]:after {
        --txt: attr(data-char);
        -webkit-animation-duration: 0.2s;
                animation-duration: 0.2s;
        -webkit-animation-delay: 0.5s;
                animation-delay: 0.5s;
        -webkit-animation-timing-function: steps(1);
                animation-timing-function: steps(1);
        -webkit-animation-fill-mode: backwards;
                animation-fill-mode: backwards;
        content: var(--txt);
        color: hsl(0, 0%, 10%);
        position: absolute;
        left: 0;
        top: 0;
    }
    @-webkit-keyframes glitch-switch {
        0% {
            content: var(--char-0);
        }
        10% {
            content: var(--char-1);
        }
        20% {
            content: var(--char-2);
        }
        30% {
            content: var(--char-3);
        }
        40% {
            content: var(--char-4);
        }
        50% {
            content: var(--char-5);
        }
        60% {
            content: var(--char-6);
        }
        70% {
            content: var(--char-7);
        }
        80% {
            content: var(--char-8);
        }
        90% {
            content: var(--char-9);
        }
        100% {
            content: var(--txt);
        }
    }
    @keyframes glitch-switch {
        0% {
            content: var(--char-0);
        }
        10% {
            content: var(--char-1);
        }
        20% {
            content: var(--char-2);
        }
        30% {
            content: var(--char-3);
        }
        40% {
            content: var(--char-4);
        }
        50% {
            content: var(--char-5);
        }
        60% {
            content: var(--char-6);
        }
        70% {
            content: var(--char-7);
        }
        80% {
            content: var(--char-8);
        }
        90% {
            content: var(--char-9);
        }
        100% {
            content: var(--txt);
        }
    }

</style>
<template>
  <NuxtRouteAnnouncer />
  <header>
    <span>Langdex</span>
  </header>
  <main>
    <NuxtPage />
  </main>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-size: initial;
  font-weight: initial;
}

:root {
  --font-heading: "";
  --font-body: "Inter", Helvetica, sans-serif;
  --font-bold: 700;
  --font-scaler: 3vw;
  --font-xl: clamp(3.5rem, var(--font-scaler), 2.5rem);
  --font-l: clamp(2.5rem, var(--font-scaler), 1.75rem);
  --font-m: clamp(1.75rem, var(--font-scaler), 1.25rem);
  --font-s: clamp(1.25rem, var(--font-scaler), 1rem);
  --colour-white: white;
  --colour-white-1: whitesmoke;
  --colour-black: black;
}

html, body {
 font-family: var(--font-body);
 line-height: 1.5;
 scroll-behavior: smooth;
}

.langdex-heading-xl {
 font-size: var(--font-xl);
 font-weight: var(--font-bold);
 line-height: 1.1;
}

header {
  background: var(--colour-black);
  color: var(--colour-white);
  display: flex;
  align-items: center;
  padding: 1rem;
}

main {
  padding: 1rem;
}
</style>

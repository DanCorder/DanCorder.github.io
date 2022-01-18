---
layout: blog
title: "Svelte and Complicated State"
---

I'm currently creating a website to help with the creation of cryptic crosswords. As the site is very dynamic I wanted to use a pre-existing framework to bind my state to the DOM of the page and decided to try out [Svelte](https://svelte.dev/).

So far it's been quite nice to work with, but one thing it's taken me a while to get to grips with is how to update complicated state. In my case I have a large state object for the clues and the grid of the crossword. Updating the grid can effect the clues, and updating the clues will effect the display version of the clues below the grid. I also wanted a button beside each clue to write the answer into the grid. This means a lot of dependencies between the various parts of my overall crossword state object.

I decided to put all the public methods for updating the state on the top level crossword state object. This made it simple to update both the grid and clue state objects as needed. This did mean that I had to pass the full crossword state to each component though:

    <Grid crosswordState={state}>
    <ClueDisplay crosswordState={state}>
    <ClueInputs crosswordState={state}>

Svelte notices change to state through assignments, so it will notice something like

    boundVariable = "new value";

but not

    boundArray.push("new value");

That meant that all the crossword state methods had to return the state object so they could be used like this within the components:

    crosswordState = crosswordState.toggleCellColour(row, column);

However, this still didn't address the problem of having the ClueInputs component notice when the Grid component updated the state. One way to solve that is to [bind](https://svelte.dev/tutorial/component-bindings) the state to the component.

    <Grid bind:crosswordState={state}>
    <ClueDisplay bind:crosswordState={state}>
    <ClueInputs bind:crosswordState={state}>

However the Svelte docs caution against too much binding. I also wanted to split some of my components down into smaller components and I'd need to keep binding the crossword state all the way down with this approach.

In the end I found a blog post that suggested wrapping the state in a [custom store](https://svelte.dev/tutorial/custom-stores). This effectively makes the state a global variable which feels a bit yucky but is definitely convenient. The fact that I'm using this to just expose the update methods makes it quite similar to registering some event handlers which to my mind makes it seem a more palatable :). Using the update store method means that every component using the state will notice whenever it changes.

    import { writable } from 'svelte/store';
    import { CrosswordState } from './CrosswordState';

    function createCrosswordStateStore() {
        const { subscribe, set, update } = writable(new CrosswordState);

        return {
            subscribe,
            set,
            toggleCell: (rowIndex: number, columnIndex: number) =>
                update(g => g.toggleCell(rowIndex, columnIndex)),
            setAnswerText: (clueNumber: number, direction: "a"|"d", answerText: string) =>
                update(g => g.setAnswerText(clueNumber, direction, answerText)),
            ...
        };
    }

    export const CrosswordStateStore = createCrosswordStateStore();

This store can be used in the top level components like this to pass down parts of the state:

    import { CrosswordStateStore } from "../modules/CrosswordStateStore";

    <Grid state="{$CrosswordStateStore.grid}" />

In those components it's easy to call the store methods:

    import { CrosswordStateStore } from "../modules/CrosswordStateStore";

    CrosswordStateStore.setAnswerText(
        state.answerPosition.number,
        state.answerPosition.direction,
        state.answer);

I'm very new to Svelte, so if anyone reads this and has a better way of sharing state amongst a number of components I'd be grateful for a tweet.
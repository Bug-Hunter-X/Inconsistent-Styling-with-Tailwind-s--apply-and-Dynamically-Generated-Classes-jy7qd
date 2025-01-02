# Inconsistent Styling with Tailwind's @apply and Dynamically Generated Classes

This repository demonstrates a bug where using Tailwind's `@apply` directive within dynamically generated CSS classes leads to inconsistent or unexpected styling.  The problem stems from the fact that Tailwind processes `@apply` directives during the build step, while dynamic class manipulation happens after the build.

## Problem Description

When JavaScript code modifies the class names of elements, including adding or removing classes containing `@apply` directives, the changes won't be reflected correctly as Tailwind's initial processing is bypassed.  This causes unpredictable and inconsistent application of styles.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install the necessary packages.
3. Run `npm start` to start a simple development server.
4. Observe that the button initially has the correct styles.  Upon clicking it, the class changes. Note that the styling is not as expected, illustrating the bug.

## Solution

The best way to address this is to avoid using `@apply` within dynamically generated CSS classes whenever possible and use standard utility classes directly.  In instances where dynamic class generation is essential, utilize techniques like fully composing utility classes in JavaScript.
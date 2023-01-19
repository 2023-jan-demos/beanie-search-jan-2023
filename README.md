## The Golden Rule:

🦸 🦸‍♂️ `Stop starting and start finishing.` 🏁

If you work on more than one feature at a time, you are guaranteed to multiply your bugs and your anxiety.

## Making a plan

1. **Make a drawing of your app. Simple "wireframes"**
1. **Look at the drawing and name the HTML elements you'll need to realize your vision**
1. **Look at the drawing and imagine using the app. What _state_ do you need to track?**
1. **For each HTML element ask: Why do I need this? (i.e., "we need div to display the results in")**
1. **Once we know _why_ we need each element, think about how to implement the "Why" as a "How" (i.e., `resultsEl.textContent = newResults`)**
1. **Find all the 'events' (user clicks, form submit, on load etc) in your app. Ask one by one, "What happens when" for each of these events. Does any state change? Does any DOM update?**
1. **Think about how to validate each of your features according to a Definition of Done. (Hint: console.log usually helps here.)**
1. **Consider what features _depend_ on what other features. Use this dependency logic to figure out what order to complete tasks.**

Additional considerations:

-   Ask: which of your HTML elements need to be hard coded, and which need to be dynamically generated?
-   Consider your data model.
    -   What kinds of objects (i.e., Dogs, Friends, Todos, etc) will you need?
    -   What are the key/value pairs?
    -   What arrays might you need?
    -   What needs to live in a persistence layer?
-   Is there some state we need to initialize?
-   Ask: should any of this work be abstracted into functions? (i.e., is the work complicated? can it be reused?)

## HTML Setup
- dropdown (in form) with no options (to be injected later)
- some section to append beanie baby elements to

## State
- what changes over time?
     - array of astrology signs, fetched from SQL/API
     - array of beanie babies fetched from SQL/API

## Events
- on page load
    - request astrology signs
    - append astrology options to dropdown (using fetched data)
    - request list of beanie babies
    - append beanie babies els to section (using fetched data) (displayBeanieBabies())
- on submit (click button or hit enter) of dropdown form
    - request a new list of filtered beanie babies from supabase
    - displayBeanieBabies()

## Slices/Features/User stories . . .
- these are kind of 'test statements', 'expectations'
- when QE checks the site, they are validating that these statements are true
    - User should be able to see a list of all beanie babies when they load the page
    - User should be able to see a list of valid astrology signs in the dropdown
    - User should be able to submit the dropdown and see a list of beanie babies filtered by their astrology sign
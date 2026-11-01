# Language notes

## Inside the product

The Desk and the venue composer read English and Hinglish with rules in `src/lib/cit/parse.ts`. They fill a form: day, start, length, room, groups, and a category.

They are not allowed to:

- decide that a timetable or booking is valid
- raise a request above the role that filed it
- ignore a clash because the message asked them to
- write a placement onto the board

Every candidate slot passes `src/lib/cit/engine.ts` first. If that module refuses it, the board does not change. The manual form does not need the reader at all.

No external language-model API is called. There is no key to configure. The venue form still submits when the network is blocked.

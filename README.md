# Speech Detection

A page to practice speech detection. Built for Wes Bos' [JavaScript 30](https://javascript30.com/) course.

## Notes

Like with the webcam project, this must be run through a server.

`SpeechRecognition` is a global variable that lives in the browser.

You need to create a new instance of `SpeechRecognition`, set the `interimResults` to `true` (so that it populates the element _while_ you are speaking), and create a parapgraph.

Select the `words` div and append the child `p`.

Add an event listener to `speechRecognition` and listen for a `result`.

Call `start` on `speechRecognition`. Now when you speak you should see `SpeechRecognitionEvent` results.

Inside the `results` there will be a list, not an array.

Nested within this is a `transcript`, `SpeechRecognition`'s `confidence` in its transcription, and an `isFinal` Boolean.

Convert the `results` into an array and `map` over it.

Return `result[0]` to get the results, then `map` over it again, return `result.transcript` and `join` the pieces.`

It you stop speaking, the `result` event is over and the event listener will unbind. So add a second event listener to listen for `end` and call `recognition.start` again.

Now set `transcript` as the `textContent` of `p`.

Right now new results will overwrite older results.

Check if `e.results[0].isFinal`. If it is, create a new `p` and put it inside the `words` div.

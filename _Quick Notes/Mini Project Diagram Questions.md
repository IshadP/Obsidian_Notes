## Collaboration Diagram

**Q: what does builder(), run_polling() correspond to and do ? **
=> 


**Q: why are there no functions inside Message Handler and command handler?**
=> `CommandHandler` and `MessageHandler` don’t have functions inside them in the diagram because they don’t contain logic themselves—they simply link incoming commands or messages to specific callback functions like `start()` or `handle_message()`. These handlers act as routing mechanisms and are configured to trigger external functions when certain conditions are met. The actual processing logic lives in the callback functions, which are defined elsewhere in the code. The diagram reflects this separation by showing handlers as connection points rather than functional units.


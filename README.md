## Task 1. Implementation of Rate Limiter using the Sliding Window algorithm to limit the frequency of messages in the chat

> The chat system needs to implement a mechanism for limiting the frequency of messages from users to prevent spam. The
> implementation should use the Sliding Window algorithm for precise control of time intervals, which allows you to
> track
> the number of messages in a given time window and restrict users from sending messages if the limit is exceeded.

#### Specifications:

1. The implementation must use the Sliding Window algorithm to precisely control time slots.

2. Basic system parameters: window size (window_size) - 10 seconds and maximum number of messages per window (
   max_requests) - 1.

3. Implement the SlidingWindowRateLimiter class.

4. Implement the class methods:

    -     _cleanup_window (clear outdated requests from the window and update the active time window)
    -     can_send_message (check if it is possible to send a message in the current time window)
    -     record_message (record a new message and update the user's history)
    -     time_until_next_allowed - to calculate the waiting time until the next message can be sent)

5. Data structure for storing message history - collections.deque.


## Task 2. Implementation of Rate Limiter using the Throttling algorithm to limit the frequency of messages in the chat

>  The chat system needs to implement a mechanism for limiting the frequency of messages from users to prevent spam. The implementation should use the Throttling algorithm to control the time intervals between messages, which provides a fixed waiting interval between user messages and limits the frequency of sending if this interval is not met.

#### Specifications:

1. The implementation must use the Throttling algorithm to control time intervals.

2. Basic system parameter: the minimum interval between messages (min_interval) is 10 seconds.

3. Implement the ThrottlingRateLimiter class.

4. Implement the methods of the class:

-       can_send_message (check if a message can be sent based on the time of the last message)
-       record_message (record a new message with an update of the last message time)
-       time_until_next_allowed (calculate the time until the next message can be sent)

5. The data structure for storing the time of the last message is Dict[str, float].
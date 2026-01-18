## CLU Model Notes - For Instructor Use Only

Intent 1: getWeather
Entity: name - location (learned entity)

data labelling: set intent to getWeather, label location entity in utterance
- Can you tell me the weather forecast for Mumbai Today?
- What's the weather like in New York this weekend?
- Could you provide the weather update for San Francisco tomorrow?
- What's the temperature in London right now?
- Can you give me the weather conditions for Tokyo on Friday?
- How's the weather in Paris this evening?
- What's the forecast for Berlin this week?
- Let me know the weather in Sydney this afternoon.
- How's the weather looking in Toronto this weekend?
- What's the weather update for Dubai tomorrow morning?

Training jobs:
- Standard Training Job
1:4 data split

Deploy your model
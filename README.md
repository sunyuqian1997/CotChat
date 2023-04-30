# CotChat - Autonomous Community Agent

CotChat is an autonomous community agent that can self-determine its conversational behaviour through the REACT method based on ChatGPT and LangChain.  

Unlike ordinary chatbots, CotChat uses the approach proposed by React. When receiving messages, it automatically infers the appropriate action through observation-interest evaluation-reflection-action. We have defined three types of behaviours: 

**Direct reply**: Reply directly to the current message, 

**Relate reply**: Related to memory vectors

and **Silent**: Feel this message is irrelevant and feel uninterested.

In this example, we collaborated with artist Nick to create a chatbot based on his character LuckyCot. This character is a cat named Modem Cot that mutated from a network mediator modem and has a network cable tail. It is interested in blockchain-related content.

![img](https://smlhic47en.feishu.cn/space/api/box/stream/download/asynccode/?code=MGZmNzkxZTJmZDIzN2NhZDE1OTFiYjM1NThiMDgwMWVfVXMwNjc5a0lHbXE2UlZKbzRvcHBDV2N2cndHQUZiRTVfVG9rZW46SkFMUmI4R05Hb2pQd3N4MEVhZWNxdkdSblZnXzE2ODI4ODgwNDU6MTY4Mjg5MTY0NV9WNA)![img](https://smlhic47en.feishu.cn/space/api/box/stream/download/asynccode/?code=ZTZlOTY5ZmEzOTI5OWM3N2VlOTE3OTRmMmE3OTBjY2NfU0RWRnB5b1lhenBVbnFoSEo5OGJZUkZwdnRGRElNNWRfVG9rZW46Tk82RmJzb0Nobzhmdnl4MnRJbmNUT3ZpbktOXzE2ODI4ODgwNDU6MTY4Mjg5MTY0NV9WNA)

The thinking process (steps) of this bot can be summarized as follows:

1. Observe: Understand what is being discussed in the current conversation.
2. Evaluate: Rate the interest and relevance of the message on a scale of 1 to 10, where 1 is not interested or related, and 10 is extremely interested and related. This is a reference value for agent's decision.
3. Reflect: Identify any associated emotions, relevant memories or users, and determine if the bot is interested or related (evaluation score greater than 7).
4. Action: Choose one of the predefined actions (Direct reply, Silent, or Relate reply) based on the observation, evaluation, and reflection.

#### Example

When I mention "Kitty," it considers the message to be related to itself. The evaluation value is used to score its interest and relevance. This message is seen as relevant by Modem Cot. 

![img](https://smlhic47en.feishu.cn/space/api/box/stream/download/asynccode/?code=YzI3NWNmYzE0NmU2ZDkyOTNjZjBmZThkMDNmMzI5NzBfMVdyNld1c3hIcUVMZGlXeTYweG5hbXNJek10Skw0STBfVG9rZW46WmFhNmJ5S09Sb092YUN4NFdITGNSdUUxbjViXzE2ODI4ODgwNDU6MTY4Mjg5MTY0NV9WNA)

Next, when I say I want KFC(fried chicken), the cat thinks it's unrelated to itself, so it chooses to remain Silent. Similarly, when another user echoes the sentiment, the cat remains uninterested and silent. However, when we mention blockchain, the cat starts to think it's related to itself and generates continuous replies. We can see that its thinking process is coherent.

![img](https://smlhic47en.feishu.cn/space/api/box/stream/download/asynccode/?code=ZjA3MGU2NzM2MTJkYzBhZjE1ZWI2ZTY3YjdmOWQwNDBfSVBDTkNZYWhMQjI2UkU0OXduTzQwOUVOeUgzRkVjS0JfVG9rZW46UmlSZmJhZXgyb1djcHV4RWhCYWNtblVLbmllXzE2ODI4ODgwNDU6MTY4Mjg5MTY0NV9WNA)

The chat process with the cat is converted into vectors added to its memory. Later, when we mention KFC again, we can see that the cat becomes interested this time because it is related to its memory of the previous discussion on KFC. But when the user repeats the same message, the cat gets annoyed, and refuses to reply.

![img](https://smlhic47en.feishu.cn/space/api/box/stream/download/asynccode/?code=ODVkNDM3ODNkMDQwOTRkYzQ3MTVjYjQ1N2JkOWYzOGFfZnNvN0VJTkpZM3hvbXptQ0lVZXhYU2VZY0plY1JDbUJfVG9rZW46R2RLQWJUSUM0b2xOSXR4b1Zud2NPMURMbm1iXzE2ODI4ODgwNDU6MTY4Mjg5MTY0NV9WNA)![img](https://smlhic47en.feishu.cn/space/api/box/stream/download/asynccode/?code=Njg1M2ZjYzgzYWFjMDAwOGMxYmQ4N2M0Njg1ZDZjN2JfUUgwWEpaQzd4eFIydWlTRDRoVEZhYlppRGxYdGpWcjBfVG9rZW46RXRLd2IxWEZMb1VLUEF4dEVXUmNQOGZ2bnNnXzE2ODI4ODgwNDU6MTY4Mjg5MTY0NV9WNA)

Left: Relate discussion to memories. Right: Get annoyed when the same message is repeated.

```Plain
Related memory:
User[User[未命名Cheese]]:Let's order KFC from blockchain!
modem_cot:@未命名Cheese @李子, I've heard that blockchain technology can make food delivery more transparent and efficient. Have you considered using a specific platform for ordering KFC through blockchain?
User[modem_cot]:@未命名Cheese @李子, I've heard that blockchain technology can make food delivery more transparent and efficient. Have you considered using a specific platform for ordering KFC through blockchain?
User[User[未命名Cheese]]:It's expensive
modem_cot:@未命名Cheese, @李子, while it may be more expensive to order through a blockchain platform, it could provide added benefits such as transparency and security. Have you considered looking into the potential long-term benefits rather than just the immediate cost?
[...]
```

In summary, we have applied the Observe-reasoning-action approach proposed in React to community chatbots. Currently, this application is displayed through WeChat. We hope that in the future, Autonomous Agents can truly become members of human society.
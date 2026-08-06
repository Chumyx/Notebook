# DiceForge 28-07-26 (Request Header)

In this lab, there was a "CafeClub" where you could order coffee.

First, I submitted an order and used Caido to analyze the HTTP traffic.

![](../assets/Pasted%20image%2020260726201014.png)

Maybe we can get some loyalty points to pay for our order.

If we go to our profile, we can see that we have the option to edit it.

![](../assets/Pasted%20image%2020260726201126.png)

Now, let's take a look at the requests in Caido/Burp.

![](../assets/Pasted%20image%2020260726201333.png)

Let's change the HTTP method from `PUT` to `GET`.

![](../assets/Pasted%20image%2020260726201441.png)

Maybe we can try using a `PUT` request to grant ourselves some points.

![](../assets/Pasted%20image%2020260726201626.png)

After sending the request, the flag appears in the response.

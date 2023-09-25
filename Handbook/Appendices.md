# Appendices

## Appendix-1: A Rant About AC

I did not want to implement AC the way it works in D&D, because it feels to me less like armour and more like dodging skill. Since no one wants to engage in even more manual number crunching in the middle of an intense battle than what we already do, that is good enough for a TTRPG. But in a game where all the calculations are handled by the computer, we can do better. The two simplest and perhaps the most common ways to calculate defence in games are what I call "cutoff" and "damping". In the former, a flat amount is removed from the incoming damage, and in the latter a fixed fraction of the incoming damage is absorbed. One subtracts, the other divides. But in my opinion, neither of these reflect reality adequately. The problem with "damping" is that in reality, something that can absorb half of a light damage usually can absorb only less than half of heavier damages, and something that can absorb half of a heavy damage, usually takes off more than half of lighter damages. On the other hand, "cutoff" armors have been given the potential to entirely nullify smaller attacks, whereas in reality we can feel softer knocks and bumps even through something that can protect us from stronger hits. One way we could avoid these two problems is by using a hybrid process to calculate defence. It could be a "damping" defence up until a threshold value, after which it becomes a "cutoff" defence. But this solution did not feel as elegant as the one I eventually came up with. And I was so proud of the one I came up with, that I finally ended up using it in my game just to serve my vanity. Not only does the defence I designed absorb higher percentages of lighter damages like the "cutoff" systems yet negate higher flat values from heavier damages like the "damping" systems, but it also does so through a single, very simple formula which happens to make the curve smooth and pretty unlike the jagged curve of the previously mentioned hybrid solution which also needed two separate formulas for damage values below and above the threshold. I am not aware of any games already using my system, and I will be very sad if I find out one that does, because I came up with this system all by myself and am very fond of it.

Here is a random graph that was lying around in my screenshots and was too nice looking to waste. It shows how effective damage decreases with increasing defence, when the incoming damage is constant. Also, it very accurately represents my life since I became an adult:

![Graph: Received damage wrt Def, at constant incoming.](Handbook_files/wrtdef-inc-20-40-70.png)
<details open>
<summary>If you cannot see this image on GitHub...</summary>

Certain ISPs (like Jio) block _raw.githubusercontent.com_ for some reason, which causes repository images to not load. If you have this problem, please use a VPN or connect through a different ISP.
</details>


# 🩸 Blood DK Tanking Assistant

This file contains the WeakAuras string and documentation for the efficient, single-target tank rotation tool designed exclusively for Blood Death Knights in WotLK PvE.

## 🔑 Design Philosophy & Threat Management
This WA prioritizes high threat generation, impeccable buff uptime, and the efficient management of both Runes and Runic Power, allowing the tank to focus on positioning and defensive cooldowns.

1. Proactive Threat & DoT Management
    - **Pestilence Preemption:** Calculates and cues the player to apply **Pestilence 5 seconds before primary DoTs fade**. This ensures maximum uptime on AoE DoTs and sustained threat on multiple targets without dropping your debuffs.
    - **DoT Tracking:** Clear visual indicators display missing or soon-to-expire DoTs required for maintaining optimal threat.
    - **Melee Swing Timer:** Includes a dedicated **melee weapon swing timer indicator** for coordinating abilities like Rune Strike with auto-attacks.

2. Resource & Buff Optimization
    - **Runic Power Dump:** Intelligently tracks Runic Power and suggests using **Death Coil** when Runic Power is high and **Rune Strike** is insufficient to prevent capping.
    - **Mandatory Buff Uptime:** Provides clear tracking for critical buffs that must be maintained:
        - **Horn of Winter:** Indicator for full uptime.
        - **Frost Presence:** Confirms the tank is in the correct presence for threat and mitigation.
     - **Consumable Tracking:** Displays a prominent reminder when the required the tanking potion, **Flask of Stoneblood**, fades out.

## ⚠️ Design Limitation: Single-Target Only
This WA is strictly optimized for single-target boss encounters. The logic is focused on maximizing threat and resource management against a primary target and does not include complex AoE rotation guidance for trash pulls.

## ⚙️ Modularity and Configuration
  - **Fully Modular:** Everything is designed to be **modular and easy to configure** via the WeakAuras interface.
  - **Customization:** You can easily adjust the visual elements, timing cues, and link your preferred tanking potions or specific raid buffs within the WA settings.

## 📺 Demonstration

https://github.com/user-attachments/assets/68abb5ad-2411-4f4e-befd-b68e11792d28

### 📸 WA Layout

![Blood DK Tank rotation](https://github.com/user-attachments/assets/e259629e-ee39-4b8a-b560-0c8a8fa64fea)

## 📥 WA Import String

Copy the entire block below and paste it into the s `/wa` import screen:

```lua
!WA:2!LJ1AqYXv1zVAqyXaLJ0i0I8IX0wqPYRT8QDh9YYLLn7S7SAx59L7zwTYMOS9R7oDRTNUBD7U3xabZAJqqIdKnogeXyGnjkGbNuEumYoobtTMhXuvQCyXjyhc8J9hqv8tvf8x4CU3UNz2rwgHWPQuf6hA75o375E7Z3JZ5oTD8CH1oqx57URdPuGfPNRAoRCwN9WlRZnhM5vjY(rAFDdFUfJxq3CglUFqWwl46S4I6ClLY((UrobgZPxXFO(xEux2P7HD0Up0A6Xr2(8XcIC89cZYxySPNoKf9YlvH7yvEHa2Uu7F5qM70J774fvy4IduELPJDD7ZHB6Y0wI7pxPaDtwM8XC3GB0okki8U27EPTPlh)9owOJ)ew7p(0CDtXoCq1WiDEu2coEorznMg)tOD2LI4ovQW4HDSBEYJNzflMr80ttNb(GfhE8bMy4cr4hu1J565xkmG56oKvy21dJnyZY8IkHZ2z(At1xVLkpvPY9QwUqmUjgbU6lW41N24Cgon1sJxC4HvfJymit3nYw1tVklm7YXEjhHS1m9DJR6jFbVe((Z4E6UhhpN4RYtVuCiByNQorAQ6Uov8m6R4OLlQEPqFE0Glyq5pDdx25xFaUFyKcUVHmptMDqUbC1dNrXFALiBMYO40TTxEiZfqqk2eFSGRVpIy6b2RmolmYXvSS1h0N7rlAsXbXEv50kHh2zy2RnURELyw6hxTFMEKD6Nwr(P(8DCTlyXcnNVT)PY2oHktY0NPxmDgQeA7pxO484XMpsrKDXpQhPOJFNUL)CkbCh80qZm21sXupmQRSzhksjcX2zKRLZQQJiQxfflmQeGRO7HZfjFye8sFLN2311FoAAI9j8Uu0oUE1ahUJPmhOThfTsYDDsKrFxkJJHLgSF2S(XCALY3xCmAd0gXb))cyAnsdpuJ6hXKh(wNpESXtHN7ckgmf9GaxhMLsKpoeUaDEfw0EWfIzMWiXQet10MrVGor4hfNFZyoh5njRa3WY4GjRq3n0xXXZ0n2c3bfUUxfMmcmU8WIXb3alNqbX0sUhZzZWCLYSitYkjU0SqLhZmIz1fk0Iej024Zk5FBEfKrRYQi0TgCDlN4Wh5DOgsK1nJCdDRbmI0rUtu7QvJrXF2cy22SD4EYQAIzQq6PcHolYOhww3ZPQydoiSTbGDwWdtjRY0dzihs4UC9RLIPtrYqEiZ03ZkCjAoKif6Rab(4AH(G(VEOimaCu8XT36iRzKyp1NVRp)yzYKz8mD31bQj9UgYdTFYWLhhMwnDpt0Fs4(aDQgAIVrzwXKrsaH90WQgYfAVI8VfTQWc2wPthRZzkdGwvktA7eXwomIf0Rxfx27nzILWx9nR6sk4DScxKiPiUQ1cOrGJzfUFCaQSdS1ZyeISitMHt1auTUm5noPJvK9BFDmhGgAErdG(B(Cd1E7FOjkLp2XQwNrtoGXWhpYDrJvLBO0A9TzeYQIyOApD1Dx9SsKVzcGULz)J3LJfV)7dL(EZuGSrG(QnnhDLqmqpspZLKjJbOHOJQrP(ulwC0GTIor9kZtm(eONNTbEUM2Ps2c4BXCQQdD0blZNxU)TLKOLz)2ARnmDIaPJSaqnhVP95sMq71WhnzfjpYqno(EsUITLZ8Po7EwXbxujrw5MUoyZWBv1mfnZut36uXy62Ae953uJp44TjylTbddDc3a8hvGcGg8ohD3WooBU8OZXU2x3ltE7cB4oGBFn8uGcNWsO10yERfk(ZioHHOmdEVGc0o8UwHgTpxKRgAZXSWO4A1Ue(WuYQh9reDBAGIZJiujzrdB4wGDTkTxc)hhRWou75a5pC3W7ll0rwKVEJ1Wd0yilxhr1C3n8EGBgE3WnzGbsLv1gE)zRHc4tf7Hv1MLLx3BHGTPlEUSS2Xi(wSV(1b7(PxpG7xbT(dLjRB7MUUnbfeAmurqcJuDYGx2iBV1rWsIH6rKkKzd35MHd3r7WoxdTbiffXx9SmSzovSJocC3p(YuAWdRWXTHJGA827rRgn0SmBhS2Tn8b2TbLlDz16VyVLh8(gLOjW9SB4r1mgxDOILkRTcTaPlITiEcNd5WM(vn0J0G7L8pGEP)xYetaCb(BdNaEGwh2XZgMaMDP06cARM(ejETHRpl4KftOny7JRtgU2GgORohP8osHf99R2wbS9fFnWqQDGBhyzGjZatdva32GtwlS)5h9yd27OgODHJhj0WWVvk9FPkyjOPeQlHF2Ytm6qLhqT3rkUS4BOXwZiokY3BmCDOvn3YFk6RSRjMGSHMcebe2(SWxYEDBhl2u6UUIzfAdFzyf4jwteZsfhUyFLhtfEs1XDMN5UcglKLhQJVUR04KeKREf57AyNPzutaqUSqwuZ4Lf83neOfStSxdFolPLnH6SiN7Zd1U0mm0JJC5JujfS9z3dWLYtiuinHOnbX1LH)12WSOe8pribH5qbimFhq3WcWIPcm4dztYb4Jyd)Pczd8r7aEiHEafkFyn4JHQdu1GIdyjsxKgREsJ1QsHBVc1bn1KOIRTrqPLNetA3OGshaXETKggw4HHhb(4cffCMMerTuSzWF7LFGprdTdCw4tssf4tvxIa)z2jm6pTn8z0G)snuNa)5WJkfgWFHMKQdllO2WFLGklHg4RQrwBsQx8XmFq9Uh)ONk(eWJBdNttWk)CTrC46e2Uj2kYz)Shrs6H)Me6j8eWxaEs4lI8kbpcjbij7jG)o4VvoW)a8vWV)VhoVnnLecYJPbpvZGogZwb8x3OVXqJdMezAtWDUvgYEemecV2iwQvhlR7J2euQEWd1DphEJSer8c2E9gIlHYnMb1yRylAWw2ihK2ckGhi)boqt8qAFOtLylGhopQf3iNHstxo8FgcNr0EJKGwr9MS5sXEeNtGFrIpvJHW4JlSQsr8Z1WHApnaCKICNh9y9hpGXHclta)Ss2tQqNytxRvko7DCf5a0wqKGScofcU3mcg)myNQIAHuQDzXtuP0TS6VmyBKxFfMhAGAklfRT2g(OOgCVUZPVqiL9xJJ3MQuAeG7ynA91JOgbxiojQerlSIPLgHZ3sWn2x61egpPKPYTkItNcsGG08Rs5c4Xe7SXBmS3znbvHOfe(JHcjj4MmFh1Kx8AaQei8EmKDvt8M93Z(qEdsAANpyVQJG3SK4ljmLNY(nIMiX)xFMs7nOjiBkHJGsU6OPKSulP1)HWgG2ukN5K1oXGZm3ibbL7ECrTlKbrShKTSrc0DiiwsgK0VqsTrYJ3TTBvXnnoOkEpIywBlnRo3HUd6QYBl7Ps3gb2rgUPn9eEDB4LowM2g8EFOTk(xMLWUvWUEIwac3nS6bHDGKOVDWw1JIWomOiLKeFP2GVlMA(EWKe1)A1k(nGLMuA6Mfy(oHAWf2cUNjwl)ZKrZ)IaUFEn45eCQlc5j2xqozhl0PuLD6yhod5xpl8nAHdHG)8DKCfA5vdHx4kqKK1M(3OIrFtb3RD4f3iF5AvL(7Sxu7xbJiPEE7cj9JLYZi(aHHyE7BdFhe1riRv8grWMaA4FVzGLmkqg2BaxmFtCXtwZyIdTF(mvV)tD)pqdAzc9(BTPgQauDD11xY)ivLy7QIFFb4CeQt4iIliOFHT8D)8cEXlRjS8t5dxe2RKqSu6TvZ1JWSi2t8B9aNt0gRiMAsor7WZwt2JIkt3AbAt3fmxUdqv6(xf3LqErelvmg20X45TxU(V0rU8cdoSfzEeDNm7AMyBU(vNI6gunYPkZkDeQLs8GIhvH7x9(rF21LBFQ)N4f5)ixEbR7cB5f(10V00u0VLfDIFrXIrbmsXdfezmJ8YARx3MTp8EayRYVGwqU6NYP8tUlZUU7JioV1)gn4IR04xpjrmjkCJtffeFnzRDAjfTRNz((WpWg(FP5882WA4H9hAdVc8FjMnbg)i89cEv6S9)ydVMM49q8srQhuQrBb9EI43pwKuPx2)BCPxe(PjNcQQoTb)enX5iPpqdz2miN8Vj33Ay)koMbhBAXnY89U1KFcVoZQG)JZWln5PKm2hSNtk(DysNZhm)jv851)29DYoZY8S()SMnppxEFQ8OM(zqj9ZODL7(uW(CIyvjNSaMvlobxDnIo6I57Db1t5WloXvUr09EfAenTlbrdMs)e0iH8teof)U4NiBoTHLpE4E9Aon1hRjVFsMUrRFsY3K1)(tPsKbXf2YQ)CjB9mIvUtC2VMMAG)CmEh76GDVU4P6kIo219CeHNGyym8QJtpi2I))Llp6j(MT5EI7BIbpltR0I9t0Ljtm4TCgP8OlgD4oZxPHbpYwA1C)neItRQF2TrgijE6jWjwJ)Tia8utKlc7lbJtWxKb8FQ1Ou(3iTeGioVk5ZKSeAk3YA9kmduMiKADrSlIT41bwFtrAFT1HyZYSwAvKsTyc(K1MGnub1W(NHxDKFRy2(AGzn3GO4Qf)(rAESRc8Dds4BGa6TIj9N51srkcAtbEqc82jy87lBsj8UeGVeL)dCbyxnla73(etwPZfmD9331OaSXL)AYKvGqVu26kpeLUmPzliupnHqyeoFl6qAr0KEonzKVf4xC5W51YLXVsids8Etdzqu(Qay6PzGHF8(o(yp4eZENtm9veyUwzV5M9voXV5p
```

## 🐛 Known Issues & Support
Please report any bugs or unexpected behavior using the **Issues** tab on the main repository page.

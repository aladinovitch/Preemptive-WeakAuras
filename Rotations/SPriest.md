# 🔮 Shadow Priest Preemptive Rotation Assistant (PvP/PvE)

This file contains the WeakAuras (WA) string and documentation for the single-target, calculated rotation tool for Shadow Priests in WotLK.

## 🔑 Design Philosophy & Core Automation
This WA is built on the premise of **preemptive sequencing** and **dynamic gear-based optimization**, moving beyond simple DoT tracking to identify peak burst windows.

1. Max Power Indicator (Burst Window)
A highly visible, glowing icon acts as the "Go Signal," indicating the precise moment for maximum damage output. This state is contingent on three high-value buffs/procs simultaneously being active:
    - BiS Trinket 1: **Dislodged Foreign Object** or customizable alternative.
    - BiS Trinket 2: **Charred Twilight Scale**.
    - Full **Shadow Weaving buff stack**.
2. Gear & Talent Optimization
    - **BiS PvE Logic:** The WA excludes **Mind Blast** from the rotation sequence when the user is equipped with BiS PvE shoulders, reflecting the most optimal, dps-efficient spell priority for end-game gear.
    - **Configurable BiS:** The system allows users to input the name of their specific PvE shoulder item directly into the WA for precise, personalized optimization.
    - **Trinket Flexibility:** Users can easily configure the "Max Power" tracking to monitor the buff from **Phylactery of the Nameless Lich** instead of the Dislodged Foreign Object.
3. Range & State Tracking
    - **Range Verification:** All tracked spells display a red overlay while out of casting range.
    - **Mandatory Buffs:** Visual cues track Inner Fire and Vampiric Embrace status.
    - **Shadowform Check:** A visible icon confirms Shadowform is active while in combat.

## ⚠️ Design Limitation: Single-Target Only
This WA is strictly optimized for **single-target** encounters (Boss Fights and Arena PvP). It does not contain logic for AoE (Area of Effect) trash pulls or multi-dotting sequences.

## 📺 Demonstration

https://github.com/user-attachments/assets/b40e490e-3567-438d-9c61-5813c7963691

### 📸 Annotated WA Layout

![SPriest rotation details](https://github.com/user-attachments/assets/e553ee28-413a-4a72-b44b-cd1f8145bffb)

## ⚙️ Utility Macros
These highly efficient macros are recommended for rapid buff application, especially following resurrection or during pre-pull staging.

1. **Macro Solo / Refresh**
    - This macro sequences key buffs and ensures the correct stance.
    - **No Mod:** Casts !Shadowform.
    - **ALT Mod:**	Casts Inner Fire, then Vampiric Embrace, and ensures !Shadowform is active.

```Macro
#showtooltip
/use [nomod]!Shadowform
/castsequence [mod:alt]reset=5 Inner Fire,Vampiric Embrace,!Shadowform
```

2. **Macro Solo/Target Macro**

    - Casts all long-term self-buffs and ensures you are in Shadowform (Power Word: Fortitude, Divine Spirit, Shadow Protection, Inner Fire, Vampiric Embrace, Shadowform)
    - The macro resets after 10 seconds or on target change, so you can buff a specific friendly target.

```Macro
#showtooltip
/castsequence reset=10/target Power Word: Fortitude,Divine Spirit,Shadow Protection,Inner Fire,Vampiric Embrace,!Shadowform
```

3. **Macro Full Raid Buffs (Consumes Reagents)**

```Macro
#showtooltip
/castsequence reset=10 Prayer of Fortitude,Prayer of Spirit,Prayer of Shadow Protection,Inner Fire,Vampiric Embrace,!Shadowform
```

## 📥 WA Import String

Copy the entire block below and paste it into the WeakAuras `/wa` import screen:

```lua
!WA:2!9QvA0XT11zdnwEzKBIeLfTeLImSCeRKSnnxefTuSCdhQHIuMBgZqjVMbyaECaSWaabGHKJIJBmRTIA6oBJtB6w60w7UyhxpDlnjUoHPT2Un9CUh(d7XBDHNttBAs3uBLDQBwU33dygUjz5TOFmCaWdV399UF3VV79os6OnfuT726S926rofluRPInz0KXPLNpVM(Xn8D96Z121)ijsKySeT3w3EnP76e67ABZm6Z0Y2WN5SN5gZ3IfekNV0eteSq0fzm1mCNsEH8U(gm)urZM36tzBDYtQ5BiN111o0YRsOR(Km)alxNlBY7wjqxZMLy2aM9eJ5A5eMVV0JKnTsEX0ywr830gfyEBiZjkP5ZK7VKTT8XmTczv8zfW5jBzpMsbF3sErdpJ1jzR1B9bM4Wn63xRiBi2KmBZQIhl2IsssjMxRuOPR)OEH40eK0V8O4oIf(C(A687SpLGqn)WK5NWYXkWmzk8pHjNj03QqbCp0sR(rF9uvmy0Xbzk(dKEOX6F8Hsfs2LwjFToNjWJzBpOrqYfckLhTfNWm4OTMUAU(6nt2CzY2Rs2uLWjpVNTwzMVIdA0bjv4dn)amn7qZ6V6y(m8vvYmw6HgA2sorMqYQAo64MHFmcR7m4NmFhn7JkoSFC)PfBoPz1CSkQr7V9bxv)ZX0cyzcr)AHqZlf2Ekhxh28gOvtJihTh8dyikWiygAO0oeApvrnlN(HBeFbODOdOtOl8VBE53zhwg5f4J5eh9ct4Yv0S9m1sCgHfZ9q08MptFkPtps1jOBG2KwOwI84spHvHKr(UbDW3prf8OqH77ds2zjlJQ3K3HvMEI7S723B6kKTAjCOPSD1m6pFiIXCcBwPyjebMmf6m0Bg6lPIUTwqa9TubiIH(svlNjC9fNonxf)QolnDKhO2K(lD6UNvZxFi(j1d2mK4alOW8S5idwrCqERpki4ymTjTCki3vLH1Mw2qROwbgCjWLM3dbKOZPByt32zcC9dhOCEFlJSA5TzTc3QjCeZktGO7(S81TzQkbEA6S1cnJ(PKWMtcBjj0slTcB9uW2GpaEoF1GCs4AGDaxl8bHDMeAf(HHDb7g2tYQ6U2Lk6KHMGe591mSkf8Gxb0g5XxUxBVV5(r0FzvWbwhCLj9XiccUjbhmjKm1qP7plSrEWe0B)qk6qeoe)Z08p7N)5bsaRPoPYm(UtjSmFbuKPcFOKWLNOIoJaTeuyhdPaxHj8dbVVzdczE96uWMD1WgwBk6ydXFy4(ukkdE4bYc3s1tmGcRpJB9yMbdb9KqX2QOv46waXbOT6e2pgm76NxP3dn44zMPaDGtlGYHG9D5W1)4WLH8qiqfUy49pNrzmWZsNtMmln0JzzeAUo4MG9NpWTechYBv0JmHBobCdsW1bRBMsbSHOv0e(WjHd3mmGkUbd5qiPtVRkwODKH)QB7IGHHlUQMX9wc3tgi2ynnUWYznWM4t4C6itjcJCiwp1iV)w4aGwgb9(N(QMTefYIuSbMZs8lCYIwMNqJmcnsGr88Xzuh7YQe4iFaF0n1nIlkM3YHnSRbRsGP7ud5ofgDs4j(L9zJr)bM(4cmcoPMNb)sob1wFuWI5C06XzZSmcArP7E23(2)cIzFuKPqdpPB6M5qtemsVD6PXJ)mc6p1QOZw3mNUlYA1u3eKvaG924IEqJ5zE(DzbzqlBuN5c4)PxKAEsgHZZJtVcROjH3nScU3so8h1PMTT3g04FpRGBK2Up2fHo7ZCCgcMicGqfYdzgfsqyDeYVOqILDNnV87Ge(bAHenjZeo4bAg2(8iPePIsGhhJtFvEnfYMomxaNt42JiF92c)M8pemn5cI(c0(S1F2o2zG36x0R3qYAbXDJ1lt174zh1BJ8BIIzUe1Loh0MQx8YZiwiRPzcK8dmVGY9oImN54pNGGwtugJV3UpUjO7vH)a94KbsmBKftSC97BDs5BRKMbrqlNn7QSN8I(IsOvrMXsojIxAVDVkVfn8CrbH5cn9rSigluEE(OMcvaoMVM3mhl6lcRFsRalKav17AoxtONpt3Iebt4T9Z1yexjnN48jNhD46THbhzK0k5snA2SJomNTz(6NdusgBj64m2724P8ebgD8Sdn4iP)6ZxW2DQ(9zNOeZrV8yxC7T1z3IJA6bZrFCOib3eZqxrV985lfg66mkMSeMsqf62cPNnvL(E8X4S0f1tAlXCymXHJVJj)Hz4PyXTHSMw6hhdWdsWNJyZofDHyWdHKdbBGVAPePGL3KzvWm8GqVpcX7KZbZbX3uW0xLUXKmCwTXOaoTpFmCHvvo5bMMwrCJB5XWW)fDrlx2FXRuHpwKrslufs3A(alIMp)ykdMot26IhERhhwVr8KCAttWayl)2woMW7pfX2UGNVBbe6eiOD3Z2UO1mtmNQk8uQi5qJ8ogJljBQ0aQJICPoPRBrjsukwC4iOWcQIPmfffDqspa1D2TDXY90Lrhgd0UVLdLvlEkGQcF4wAvb5T0pE)WwtSdxVDCWdoZKA(wKop4PmPMDjwtD7RBQ5uajUBEg0Gr4syzOhHacKew3P3fykumaR1a3BS6aCCtCleRea2MqXwwyP5Da3hNlVx7P0khqKSEix7jaFEwdbMC25sM1tCWvLN4WKTO0r3D2DpWjXrpnsIJuZOB5JIFdfrO0kUFIPf(rHpo8aCYuygZ32zua)yrSMWdI7IF5eWPW79jqAp40IKj(XHpj8ta)KWp1da)0sWpdXnb)SWpNWdnl8Zd)cWNcEyj4Zkb)IWVe8BavGpJk8Rib)QWVg8RVf4txgEiPVo8BghTb)wWVDc4rGhf(D2e87kb)EIz6ZjbpEc4Xsa)(MWtyc)bBaEstOkb2H)Wiqo8hzIGt4pd(c0f)XQWFIk8NsWx4ZRgLQJijNVihxcFjehcpf8Nt4Ui35vMe(YMljpUVIy5NtcHr7BxMD23De2tV3HFD82TkWBCG2x9Ges8V0Kqfe2c(RAGRGNf9wpd4bpxlnd)1i(5Pjeye2bHIlh6SKSjUFed9iKtUylNj7uw2uCUC)2u2eCibHoIYWK8)isIGoekApjj4xtGn9UZNPKFbkF3XWKj8H7d(yXGU40uNEh3YbjawpDSV92fLWuwmbje6slcn74IqlaIZc55RiGA4smj)1P7qOCCzyYUteTo4qlBgpR7DrM1vjml4VHG208sMYjJmNi8)00z3hL(yNCyUica(BjBGcvI22yycTDQBsRk6)TEYdVRH(ruoH(rK)djTiWpguGbeV5OFe0Jq)hNhg8eQlc9)WNh0V5fcU)P5SuFzbML4WMBj0PdfbV)QXuPD7w6MoIT2rgkZDsiDmGjoz6OqLt)HG7cUBiXNSIGSJ0Rx4OAf9S8T0LZ6ws3ScQbyiNc1EWKuoeBsK9NJkT1kuIAFqejjkRDa5XW6xNLp((j11bDCy(Y9B5JYk1N00fXkN0fvUnLwb3bp0SJyZorhSd3EpKfgfvn2AJla6Oj6SKVT3wmdd9coWnEJ0l1ML7nokM7X4g7T0jUakLlkqlo8dHC3wccTLeghYGR2OQcHprT(m)XDWkpsHjJQpT0tG67bKkWX7LYsxMubcKdnzYoyEjY802Xl1cL1KfjJj7j6EdoYs2gY64rxBjtoyOmw8nMsp)D9zuX(0jzCxbK1WZTyfvkGKg2eU2ysd0W4RtWbKvxQ7r96LvxHpGU5YDv49OfqTH7ufnQrCdzcJF5JhnB0kWADKZZK18WsYzgYHU4TWxqd5mcVE8fXtMGq(BXhkxFoq2keVKB)6L8PmbIEdCbZI3m6n0SdCLTC0TlzGRGSpPBlMbMVWyX5bxaSkeE)BmeRXuMm8Ssg17TmIMxAuyY7y9hmJ2Gcs(r9cBTu50JCkOMj8IMWRAcVGj8sMWlBcpVj8kMqwjQ86(xr51Iy0BEXLx)2xtMIIVLQ30Tp8DouHYfoY(lI1Kd3EJsXH7GkbhUtCO6Rdd2ZtHWhtfYbQymE3y905dyfXDKshT1EBDupAFTWhztuapfQR8Gxbrem4d2mjpPrLHxpsFc1tFdCHR)o4VNcWwHYv)NHsmnhV)q8wtn74Jmy2(v6D408Sx53dEuFd3C8uA5z5Mt0mVuu0aS5jHVL5cMwgSCyzI8rHkc)BW)o8nMNppzspu6(YoQc8nvgdlBYUcoxOEyGwbMzLgRUxt1dZoWqwtWKZQ5XdQ)iyq9zHTRWdc4b3yu98fyi)ILUOqw4R5TbkZ3LCtucYBl9fhtnwugSY7Ix68UjAbEY20MOGUH688lONr1PRIShZ7Z0SZeFh45JAkepFCE0S6S1h)LDZNiwcVtm8EhD1oPx(8W9nVOg7HTcOCX5tXstASSq0ENjJ1TdvRIZWIQ9xKh5(B)9Kug)NW4Kw46MCzQtHcs8IieD4Zmw1Q5NjwH6ZRwx9Qz4lOUuflHuvKU1ttLgq5lDdCLku6kkhnuJAoPuuX1Q1r0p)Isp7Fg(xWOMJoEPU7D4BYPJPkscy)dW)igsSwo2UveB7TzRcoU(SOwnZBQyAFFx)arY(NFCFDjJph5Z2a8AQWzHVg)e(BRgPG8)Y9iTcVo3R9gWla)FeSaDvCGdwSbY)ey61K48IiJuOAX8XcZG)Fv47CzFj5iqXwRWrk9XBtt7W3DhDWXhVGxt11cY52WJtMY1MxmLZwFe0l9AIPTM0LycBZFGEvgU)XhYB9r2sJ54w4WR7d(EiCAH6iB(6RwT(1dAOY3FZBgV9Cv9JMRMAVM0fTJB(G84I62GQ3gBmtlE5IZV8uW9RcF3M6KV(0wuml80qRjLe2wnPRGJGZRJ1z6w0RjXFJ6R0qUfS09oYe8op56SROwXV7KY4)8zHL8rTfX9URoUhUqr8yURoVhzx)6pTR7z3jzogllm5OC8FxrXa34LM3djfyHvZJ7hD2Hy6ALFRe5ShrgNxnLX5Ni1o7Qnpp5v0pKoBBPDeHsRmkRumBZgjM6DTN7xTrdxIsFDvgCxRCWRI101YSgVTUQRAuh0(u88IXuL9UUZ9mTY2lT4eRPcjFyPv597888(ICWxfBRRfBBpeLF(6e5N71652aTzf00lNBcBxxFvop3KuI3n42QjTgZLsRTkPJ)wGCRMuIguBVWkO2cgyKID07W3M9jMAjuB7bReDFyLOWZmNi(0rHsmcEwjSA0wHN9ijKg4h5JVE()sGfN(veJh55EgV1RfsnnM6iIG4q8wIAy5mM1Kw7BjQXiHxKhms0foBvHAMctd9rVMG8avUEdOwe343wuFiryYza)IFVigWTX7DLO9ZgkLCyMCAO6n55SliM6ybBQM2C0VFNkoN1KwhYOStEnTC(iuCYN3rqtIjSQGcrKRsRXS31K2GkzJOHxt69Hd8s52B8GPmwqiudtNm2zItihxoXEOM0Lt0xeJvNAoLFVr19r8fYTDIiWNebGpP6k0D5i06Tk552(7oIWlbNwBf40rDvgC3JBpUxNPoh40Asx7fc6SM0h8DmCKRuV(6AZe0lU8Ui1BYJHaqU7K7U5qZxmsl(XIqIBIlpHstVi1ndCiNevK5YsyMdKQfVjgyAzC9Q4gQmjVPgYjjX0HB8tRG7IlcfSjH26zNrlYoRViZhsDMjoDoeljquCiDv(plw0VEt7cJmWuH)gKApAeZtPh(60QE4gJ1CHOF1P4YvHZwtAxcdMmwQFlK5qDAHVZojPMVHOThQwVt88PdE0bEeqhrIqGjtkuR924ImS6M(b5Q4O8ofmutAJ1KUYAsB6DXiILOMwtAZ1K22Ifl)SslsSSM0wJLcRj1scsMQM0hG(ylsKEvnPREjQqFgvueQM02lh3CZAsYlrb5txUM018dEXHxCfbDDUFLE7ESuPDZ037HbDTvpOB590KwWlKapmYzPzn3iUtKV8lfjb8DeXeNLk6H3Au8jiSJIzI)91RJCrqyzEqjw0ZE7ORU7w0GursJIoKgfy9sXTfve6YN6YXTDSM0(5ZBuBGOPpkpuArCp3OyHBKAX2kzPF7alqyacgIGfVJDHrOiesricewrOME4n9MWoXyQxIJWendePuVLQhY8OJ03e7p)XcgKGuVTJtpUz1OgYmOURJ31ni9FUGj00z3nDDWDZlwoNOLur)HAmf1wQfb)MXCrOVZlLp)NKPzfEX24EQMuROm(n0uhlMThjn3QqU)s4A8KwVOFFVohc8gWllqM(LC4)N9bNOO0ci8jVj3nt8N7mUQ6k82PZ))wLjrRD(qdQlbne1hPZPYmgN1an8uXnIL7mrFkf4f5tpWk8PVm3N2d3NEd0VXX9ME3DC07n7O7tZ6DKpvG4FxKD56F83SEobFd4Ff(MWJcFlrJI4Tqc(pI6Ae8FIp7)coJj8Fd)p1teLc8J6QYRWPoUG6KIqDM4dKwI(SOjXiJH4314vI(fmq(b6x2iQnXi7qBV3KV3YysIajRKlHdQEhkW8kRqGPK1ElnQzXdF0(p6Q1yLlW8YEl7fhzPEXx9C5fvVW8I)GZ98EQ()RUc3Zab3XXSpEqN9zp25Z900Kx8h77p
```

## 🐛 Known Issues & Support
Please report any bugs or unexpected behavior using the **Issues** tab on the main repository page.

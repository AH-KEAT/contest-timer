# Contest Timer · 比赛计时器

Full-screen presentation / speech-competition timer with the exact sequence you asked for, now with a settings sheet, light/dark themes, volume control and phase-coloured backgrounds in Apple's system palette.
全屏演讲 / 比赛计时器，完全按照你要求的时间流程；已加入「设置」面板、浅色/深色主题、音量控制，以及参照 Apple 系统色的阶段背景色。

**Live · 线上版：https://ah-keat.github.io/contest-timer/**
Open that URL on the projector laptop — nothing to install.
在投影用的电脑上直接开这个网址，不用安装任何东西。

## Sequence · 时间流程

| Step · 步骤 | On screen · 屏幕显示 | Sound · 音效 |
|---|---|---|
| Get ready · 准备 | huge **3 → 2 → 1** (any length 1–10 s), indigo wash · 靛蓝背景 | short beep, or the number spoken · 每一下短哔或念出数字 |
| Presentation · 演讲 | **15:00** green countdown · 绿色倒数 | — |
| 15 min reached · 15 分钟到 | switch to Q&A / overtime, blue · 切换蓝色加时 | **ting** (single bell · 单响铃) |
| Overtime · 加时 5 分钟 | **05:00** blue countdown · 蓝色倒数 | — |
| 5 min reached · 加时结束 | red "结束 / TIME" · 红色结束 | **ting ting** (double bell · 双响铃) |

## Three ways to run it · 三种跑法

Pick whichever fits the venue. All three run the same timer.
按会场情况选一种，三种跑的都是同一个计时器。

### 1 · Just open the URL (easiest · 最省事)

**https://ah-keat.github.io/contest-timer/**

Open it on the projector laptop, press `F` for full screen. Nothing to install, nothing to download.
Works on phones too. Needs internet for the first load only.
在投影电脑上打开，按 `F` 全屏。不用安装、不用下载，手机也能用。只有第一次加载需要网络。

### 2 · Download the file (works fully offline · 完全离线)

1. Download **`index.html`**:
   [**Download index.html**](https://ah-keat.github.io/contest-timer/index.html) — right-click → *Save link as…*
   (or use GitHub's green **Code ▾ → Download ZIP**, then unzip)
   下载 **`index.html`**：上面的链接右键 →「链接另存为…」
   （或用 GitHub 绿色 **Code ▾ → Download ZIP** 后解压）

2. Double-click the downloaded file. It opens in your browser.
   双击下载的文件，用浏览器打开。

3. If it opens as **source code instead of the timer**, you downloaded the wrong link — the
   file must end in `.html` and come from the address above, not from the "Raw" button.
   如果打开看到**源代码而不是计时器**，说明你下错了链接 —— 文件必须以 `.html` 结尾、
   且来自上面那个地址，不是「Raw」按钮。

**Why "Raw" is the wrong link:** GitHub's Raw button serves the file as `text/plain`, so the
browser shows the code. Symbolic details matter — a web server must send `text/html` for the
browser to render it.
**为什么「Raw」不能用：** GitHub 的 Raw 按钮以 `text/plain` 送出文件，浏览器就显示源码。
服务端必须送回 `text/html`，浏览器才会渲染。

### 3 · Clone the repo (for developers · 开发者用)

```bash
git clone https://github.com/AH-KEAT/contest-timer.git
cd contest-timer
open index.html          # macOS
# start index.html       # Windows
# xdg-open index.html    # Linux
```

## How to use · 怎么用

1. Click **开始 START** (or `Space`) when the contestant walks up.
   选手上台时点「开始 START」或按空格键。
2. Press `F` for full-screen so the speaker can read it across the room.
   按 `F` 全屏，台上的人从远处也看得清。

Shortcuts · 快捷键: `Space` start/pause · `R` reset · `F` fullscreen · **`S` settings** · `Esc` close settings

## Per-section countdown · 每段自己的倒数

Any section can carry its own countdown, not just the first one. Put `5` in the **⏱** box on
that section and it counts 5 → 1 right before the section starts — same voice, same blur,
same red→amber→green wash as the global countdown.
任何一段都可以有自己的倒数，不只是第一段。在该段的 **⏱** 格填 `5`，进入这一段前就会从 5 数到 1，
用的语音、换色和全场倒数完全一样。

- The **merged (全场) clock** and the bell marks ignore countdown time, so a bell set to
  "after 300 s" still rings 300 s of *speaking*, not 300 s of wall clock.
  **合并全场**的时钟和铃声刻度不计倒数时间，「开始后 300 秒」响的就是演讲 300 秒，不是墙上 300 秒。
- The global countdown and a section countdown can both be on; the section one runs after the global one.
  全场倒数和每段倒数可以同时开，先跑全场的，再跑该段的。

## Bell first · 铃声先响完

A countdown used to talk straight over the bell. With this on (default), if a bell rings right
before a countdown starts, the countdown holds: the digit blank, nothing spoken, the phase
colour unchanged, until the bell has finished — then it counts 5, 4, 3, 2, 1 as usual.
倒数以前会盖住铃声。打开这一项（默认开）后：如果倒数开始前正好有铃声，倒数会先让路 —
数字留空、不发声、背景颜色不变，等铃声结束才开始数 5、4、3、2、1。

- Waits for **one** bell only, at most **3 s**, so a mis-placed bell can't stall the run.
  只会等**一次**铃声，最多 **3 秒**，所以放错的铃声不会拖住流程。
- Works for both the global countdown and every per-section countdown.
  全场倒数和每段倒数都适用。
- Turn it off in **设置 → 铃声先响完** to get the old overlapping behaviour.
  在 **设置 → 铃声先响完** 关掉即恢复以前的重叠行为。

## End background · 结束背景

`设置 → 结束背景`: **灰 Grey** (neutral, the default), **红 Red**, **靛蓝 Indigo**, **绿 Green**.
It is mixed with the same alphas as every other phase background, so it follows 背景 (backdrop)
soft/solid/off and both themes.
`设置 → 结束背景`: **灰**（中性，预设）、**红**、**靛蓝**、**绿**。
和所有阶段背景用同一套透明度混合，所以跟随「背景」的 淡/满屏/无 以及浅色/深色主题。

## One language on screen · 界面只显示一种语言

Pick 中文 or English in **设置 → 界面语言**; everything the screen shows follows that choice,
including section titles (each section stores both a Chinese and an English name).
在 **设置 → 界面语言** 选中文或 English，屏幕上所有文字都跟着变，包括段落标题
（每段同时保存中文名和英文名）。

## Settings sheet · 设置面板

Click **⚙︎** (bottom right) or press `S`. Everything is saved in the browser and survives a reload.
点右下角 **⚙︎** 或按 `S`。所有设置保存在浏览器里，重开仍然记住。

| Section · 分区 | What you can change · 可调项 |
|---|---|
| 语言 Language | **界面只显示一种语言** · one language on screen — 中文 / English，切换后题目、按钮、提示全部跟着变 |
| 外观 Appearance | Theme 主题 — 自动跟随系统 / 浅色 / 深色 · 背景呼吸 breathing wash · **结束背景 end background**（灰 / 红 / 靛蓝 / 绿） |
| 计时 Timing | 全场准备倒数 1–10 秒 · **每段各自倒数 0–30 秒** · **铃声先响完 Bell first** · last-30s tick 最后30秒滴答 |
| 语音 Voice | 语音倒数 on/off · English / 中文 — speaks **every** number of the countdown (5 → "five, four, three, two, one") · 每个数字都念出来 |
| 声音 Sound | **Volume 音量 slider 0–100** + test buttons 试听：叮 / 叮叮 / 哔 |
| 分段 SECTIONS | 名称（中/英）· 分钟+秒 · 颜色 · 铃声时机与次数 · **每段倒数 0–30 秒** |
| 阶段颜色 Phase colours | 5 colour pickers + 恢复 Apple 标准配色 Restore Apple palette |

URL params still work and override the saved settings · 网址参数仍然有效，会覆盖已保存的设置:

```
index.html?p1=12&p2=3    # 12 min speech + 3 min Q&A
index.html?prep=0        # skip the 3-2-1 countdown 跳过倒数
index.html?theme=light   # force light theme 强制浅色
```

## Theme & colour standard · 主题与配色标准

Both themes use Apple's own light and dark system values, not one palette dimmed.
两套主题各用 Apple 自己的浅色／深色系统色值，不是把一套颜色调暗。

| Phase · 阶段 | Apple colour · Apple 系统色 | Dark · 深色 | Light · 浅色 | Meaning · 含义 |
|---|---|---|---|---|
| 3-2-1 准备 | **Indigo 靛蓝** | `#5E5CE6` | `#5856D6` | waiting / focus 等待、聚焦 |
| 演讲中 | **Green 绿** | `#30D158` | `#34C759` | on track 进行顺利 |
| 加时/问答 | **Blue 蓝** | `#0A84FF` | `#007AFF` | neutral continuation 中性延续 |
| 即将结束 | **Orange 橙** | `#FF9F0A` | `#FF9500` | wrap up 注意收尾 |
| 结束/超时 | **Red 红** | `#FF453A` | `#FF3B30` | stop 停止 |

Why these and not something brighter · 为什么用这套而不是更亮的颜色:

- Apple's HIG maps colour to **semantic state**, never decoration — the same red means "stop" everywhere in iOS, so judges and speakers read it without a legend.
  Apple HIG 用颜色表达**语义状态**，不做装饰 — 同一个红在 iOS 里永远代表「停止」，评委和选手不用看图例就懂。
- The 3-2-1 uses **indigo**, not red or green, because it is neither "go" nor "stop" — it is anticipation, which is exactly what iOS uses indigo for (e.g. focus states, Siri waiting).
  3-2-1 用**靛蓝**而不是红/绿，因为那既不是「开始」也不是「停」— 那是「预备」，正是 iOS 用靛蓝的地方。
- Each phase also paints a very low-opacity **radial wash** into the background (about 10–28 % alpha), so the room feels the phase change from the back row without the screen becoming garish. During 3-2-1 the wash brightens as the count drops 3 → 1.
  每个阶段还会在背景叠一层很淡的**径向光晕**（约 10–28% 透明度），后排也能感觉到换阶段，但画面不会花。3-2-1 期间光晕随 3→1 逐渐变亮。
- Digits turn **orange** at the last ~12 % and **red** in the last 10 seconds, so the speaker gets a warning before the bell.
  数字在最后约 12% 变**橙**、最后 10 秒变**红**，让选手在铃响前有预警。

Custom colours you pick apply to both themes · 自选颜色在两种主题下都生效.

## Sound notes · 声音注意

- The bell is synthesized in the browser (Web Audio) — no audio file, works offline.
  铃声由浏览器实时合成（Web Audio），不需要音频文件，离线可用。
- Browsers only allow sound after a user gesture — **click START or the settings gear once before the event** to unlock audio, then press `R`.
  浏览器要求先有一次点击才允许放声：活动开始前先点一次 START 或齿轮解锁音频，再按 R 重置。
- Use **音量 Volume** in settings (or the 试听 test buttons) to check loudness before the contest; 70 is the default.
  比赛前用设置里的**音量**滑杆或**试听**按钮确认响度，预设 70。
- Also check the tab isn't muted (speaker icon on the tab) and the machine volume is up.
  另外确认标签页没被静音（看标签页上的喇叭图标）、电脑音量已开。

---

# Existing websites / videos if you prefer not to use this file
# 如果你不想用这个文件，可以用现成网站 / 视频

| Site · 网站 | Good for · 适合 | Link |
|---|---|---|
| 演讲计时器（omikuji.dev） | Closest match: 3 bells (1 ding / 2 dings / 3 dings), speech + Q&A presets, green→yellow→red, Chinese UI. 最接近你要求的：三遍「叮」铃声、发言+提问预设、中文界面 | https://tools.omikuji.dev/zh-cn/presentation-timer/ |
| MinuteBell Speech Timer | Toastmasters-style green/yellow/red lights, overtime counter, full screen. Toastmasters 红绿灯计时，超时计数 | https://www.minutebell.com/speech-timer |
| TimerWeb Speech Timer | Green/yellow/red + chimes on/off, stage mode. 红绿灯＋可选铃声 | https://timerweb.com/speech-timer |
| Tickline Presentation Timer | Giant projector-friendly digits, voice cues (5 min / 1 min / 30 s). 超大数字＋语音提示 | https://tickline.app/presentation-timer |
| timer.media | Plain 15-minute preset, no frills. 最简 15 分钟倒数 | https://timer.media/ |
| YouTube 15-min countdown | Ready-made video with ticking + end chime (play it full screen). 现成视频，带滴答与结束铃 | https://www.youtube.com/watch?v=AQgwWZESsbg |

Note: none of the free sites do the exact "3-2-1 → 15 min → ting → 5 min → ting ting" chain in one run — that's why this project exists.
注意：这些免费网站没有一个能一次跑完「3-2-1 → 15 分钟 → 叮 → 5 分钟 → 叮叮」的完整流程，所以做了这个项目。

import tkinter as tk
import random

sentences = [
    "存在先于本质",
    "我思故我在",
    "人生而自由，却无往不在枷锁之中",
    "知识就是力量",
    "美德即幸福",
    "人是万物的尺度",
    "世界是我心灵的映照",
    "幸福不是拥有更多，而是欲望更少",
    "生命必须被理解为一种永恒的实验",
    "自由即责任",
    "吾生也有涯，而知也无涯",
    "善意即力量，恶意即弱点",
    "真正的幸福在于自知与自制",
    "唯一不变的就是变化本身",
    "成为你希望在世界上看到的改变",
    "人类被生而自由，但选择定义自己",
    "时间是最珍贵的财富",
    "最可怕的是失去追求意义的勇气",
    "自我认知是通向智慧的第一步",
    "在黑暗中寻找光明"
]

colours = [
    "lightpink", "skyblue", "lightgreen", "Lavender",
    "lightyellow", "plum", "coral", "bisque", "aquamarine",
    "mistyrose", "honeydew", "Lavenderblush", "oldlace"
]

root = tk.Tk()
root.withdraw()  # 隐藏主窗口

windows = []


def create_popup():
    width = root.winfo_screenwidth()
    height = root.winfo_screenheight()
    x = random.randrange(0, width - 480)
    y = random.randrange(0, height - 120)

    win = tk.Toplevel(root)
    win.geometry(f'500x120+{x}+{y}')
    tk.Label(
        win,
        text=random.choice(sentences),
        font=('KaiTi', 17),
        width=50, height=7,
        anchor='center',
        bg=random.choice(colours)
    ).pack(expand=True)

    windows.append(win)


count = 0
total = 60  # 弹窗计数
delay = 100  # 延迟时间，单位毫秒，500ms = 0.5秒


def schedule_popup():
    global count
    if count < total:
        create_popup()
        count += 1
        root.after(delay, schedule_popup)  # 递归延迟调用
    else:
        # 所有弹窗生成完后，5秒后关闭
        root.after(3000, close_all)


def close_all():
    for w in windows:
        w.destroy()
    root.destroy()  # 关闭主循环


# 开始定时生成弹窗
root.after(delay, schedule_popup)
root.mainloop()

# hello-world
Start 19-Sep
Finally get start of real coding after circularing around a lot of fields.



# -*- coding:utf8 -

#2020/3/4

import random

def csz():
    cszflag = True
    while cszflag:
        ans = int(input("请猜一个1-100之间的整数: "))
        try:
            ans = int(ans)
            return ans
        except:
            print("输入有误，请确定输入一个整数")

def daxiao(ans, A):
    if ans < A:
        print("猜小了")
    elif ans > A:
        print("猜大了")
    else:
        print("猜对了")
        return "恭喜恭喜"

def guessnumber():
    i = str(input("请输入你的名字"))
    r = 0
    t = 0
    record = []
    round = True
    while round:
        print(i, "来玩一轮游戏吧?\n", "继续游戏 输入y\n", "退出游戏 输入e")
        k = input()
        if str(k) == "y" or str(k) == "Y":
            r += 1
            A = random.randint(1, 100)
            print(A)
            tt = 0
            gnflag = True
            while gnflag:
                t += 1
                tt += 1
                ans = csz()
                result = daxiao(ans, A)
                if result == "恭喜恭喜":
                    record.append(tt)
                    min_tt = min(record)
                    print(("恭喜恭喜，%s猜对了！你一共玩了%d次，最少%d轮猜中答案，平均用%.1f轮猜对") % (i, r, min_tt, float(t / r)))
                    break
        elif str(k) == "e" or str(k) == "E":
            print("游戏结束，欢迎下次再来")
            return i, r, min_tt, float(t/r)
            break

guessnumber()

data = ('''玩家姓名: %s'
           总游戏次数：%d'
           最少猜中轮数：%d'
           平均猜对轮数：%.2f
        ''' % (i, r, min_tt, float(t/r)))

out = open(Users/junizhu/Documents/PEK/R/Python.Crossin/game_one_user.txt, w, encoding = "utf-8")
out.write(data)
out.close()





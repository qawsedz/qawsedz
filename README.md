import pygame
import os
from random import*
score1=0
score2=0
sround=0
sround1=0
colorhp=(0,0,255)
linhpp=880
k=0
image=pygame.image.load("C:/Users/yassine/Desktop/gamble/images (2).jpg")
sc=pygame.display.set_mode((897,504))
pygame.init()
download1=os.path.join(os.getcwd(),"fonts","font_Arial.ttf")
type_fonts=pygame.font.SysFont("Arial",150,True)
type_fonts1=pygame.font.SysFont("Arial",50,True)
color=(255,255,255)
def shufflex(x):
    shuffle(x)
    return x[0]
def shufflexx(y):
    shuffle(y)
    return y[0]
choice=0
x=["a","z","e","q","s","d","w","x","c","y","t","o","l","m","n","v","k","b","m","j","h"]
y=["v","z","e","q","p","d","w","x","c","y","t","o","l","m","n","v","k","b","m","j","h"]
w=shufflex(x)
w1=shufflexx(y)
while True:
    pygame.time.delay(30)
    pygame.time.delay(50)
    for event in pygame.event.get():
        if event.type==pygame.QUIT:
            quit()
    bot1=pygame.key.get_pressed()
    if bot1[pygame.K_a]:
        choice="a"
    if bot1[pygame.K_z]:
        choice="z"
    if bot1[pygame.K_e]:
        choice="e"
    if bot1[pygame.K_r]:
        choice="r"
    if bot1[pygame.K_t]:
        choice="t"
    if bot1[pygame.K_y]:
        choice="y"
    if bot1[pygame.K_u]:
        choice="u"
    if bot1[pygame.K_i]:
        choice="i"
    if bot1[pygame.K_o]:
        choice="o"
    if bot1[pygame.K_p]:
        choice="p"
    if bot1[pygame.K_q]:
        choice="q"
    if bot1[pygame.K_s]:
        choice="s"
    if bot1[pygame.K_d]:
        choice="d"
    if bot1[pygame.K_f]:
        choice="f"
    if bot1[pygame.K_g]:
        choice="g"
    if bot1[pygame.K_h]:
        choice="h"
    if bot1[pygame.K_j]:
        choice="j"
    if bot1[pygame.K_k]:
        choice="k"
    if bot1[pygame.K_l]:
        choice="l"
    if bot1[pygame.K_m]:
        choice="m"
    if bot1[pygame.K_w]:
        choice="w"
    if bot1[pygame.K_x]:
        choice="x"
    if bot1[pygame.K_c]:
        choice="c"
    if bot1[pygame.K_v]:
        choice="v"
    if bot1[pygame.K_b]:
        choice="b"
    if bot1[pygame.K_n]:
        choice="n"
    if choice==w:
        shufflex(x)
        w=shufflex(x)
        sround=sround+1
    if choice==w1:
        shufflex(y)
        w1=shufflex(y)
        sround1=sround1+1
    if sround>sround1 and linhpp<=0:
        score1=score1+1
        linhpp=880
        sround=0
        sround1=0
    if sround1>sround and linhpp<=0:
        score2=score2+1
        linhpp=880
        sround=0
        sround1=0
    if sround1==sround and linhpp<=0:
        linhpp=880
        sround=0
        sround1=0
    if score1==3:
        print("yassine win")
        quit()
    if score2==3:
        print("kamel win")
        quit()
    linhpp-=1
    x1=type_fonts.render(w,True,color)
    x2=type_fonts.render(w1,True,color)
    xscore1=type_fonts1.render(str(score1),True,color)
    xscore2=type_fonts1.render(str(score2),True,color)
    xround=type_fonts1.render(str(sround),True,color)
    xround1=type_fonts1.render(str(sround1),True,color)
    sc.blit(image,(0,0))
    sc.blit(x1,(100,100))
    sc.blit(x2,(720,100))
    pygame.draw.line(sc,color,(300,0),(300,500),3)
    pygame.draw.line(sc,color,(600,0),(600,500),3)
    pygame.draw.rect(sc,(100,0,0),(10,10,880,30))
    pygame.draw.rect(sc,colorhp,(10,10,linhpp,30))
    sc.blit(xscore1,(350,50))
    sc.blit(xscore2,(550,50))
    sc.blit(xround,(50,50))
    sc.blit(xround1,(850,50))
    pygame.display.update()

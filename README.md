# -*- coding: utf-8 -*-
"""
Created on Thu May 14 16:32:32 2015

@author: Antonio, Gabriel ,Guima ,Monstro, Ian
"""
import time
from random import randint
import sys, pygame
import math
import time
from threading import Timer


pygame.init()
x = 1000
y = 1080

black =(0,0,0)
white=(255,255,255)
red = (255,0,0)
red1=(192,0,0)
blue=(0,0,255)
green=(0,255,0)
green1=(0,190,0)
grey=(190,190,190)
ggrey=(119,136,153)
tan1=(255,165,79)
greeng=(0,153,76)

Northcor = grey
Riverlandscor = (176,196,222)
Westerlandscor = (255,99,71)
The_Reachcor = (154,205,50)
Stormlandscor = (178,34,34)
Dornecor = (205,133,63)
Valecor = (105,105,105)
Iron_Islandscor =(153,50,204)
Crownlandscor= (255,255,51)

slc = 1

def psegundo(msg,font,times):
    pass


        #textSurf,textRect=text_objects(msg,font)
        #textRect.center=(750,550)
        #screen.blit(textSurf,textRect), time.sleep(times)











def mostra_tropas(aldeia1):


    if aldeia1 in vilas_aliadas_objetos:


        textSurf,textRect=text_objects(str(aldeia1.lan),font)
        textRect.center=(800,320)
        screen.blit(textSurf,textRect)
        textSurf,textRect=text_objects(str(aldeia1.esp),font)
        textRect.center=(800,350)
        screen.blit(textSurf,textRect)
        textSurf,textRect=text_objects(str(aldeia1.arq),font)
        textRect.center=(800,380)
        screen.blit(textSurf,textRect)
        textSurf,textRect=text_objects(str(aldeia1.cav),font)
        textRect.center=(800,410)
        screen.blit(textSurf,textRect)
        textSurf,textRect=text_objects(str(aldeia1.lobo),font)
        textRect.center=(800,440)
        screen.blit(textSurf,textRect)
        textSurf,textRect=text_objects(str(aldeia1.gold),font)
        textRect.center=(930,25)
        screen.blit(textSurf,textRect)
        textSurf,textRect=text_objects(str(aldeia1.income),font)
        textRect.center=(930,55)
        screen.blit(textSurf,textRect)
    else:

        textSurf,textRect=text_objects("???",font)
        textRect.center=(800,320)
        screen.blit(textSurf,textRect)
        textSurf,textRect=text_objects("???",font)
        textRect.center=(800,350)
        screen.blit(textSurf,textRect)
        textSurf,textRect=text_objects("???",font)
        textRect.center=(800,380)
        screen.blit(textSurf,textRect)
        textSurf,textRect=text_objects("???",font)
        textRect.center=(800,410)
        screen.blit(textSurf,textRect)
        textSurf,textRect=text_objects("???",font)
        textRect.center=(800,440)
        screen.blit(textSurf,textRect)
        textSurf,textRect=text_objects("???",font)
        textRect.center=(930,25)
        screen.blit(textSurf,textRect)
        textSurf,textRect=text_objects("???",font)
        textRect.center=(930,55)
        screen.blit(textSurf,textRect)









def text_objects(text,font):
    textSurface = font.render(text,True,black)
    return textSurface,textSurface.get_rect()
# size = (x,y,c,l)
checker =0
def but(msg,font,size,cori,cora,funct=None):
    global seletor2
    global seletor1
    global checker



    if size[0]+size[2] > mouse[0] > size[0] and size[1]+size[3] > mouse[1] > size[1] and checker ==0:




         pygame.draw.rect(screen,cora,(size[0],size[1],size[2],size[3]))
         textSurf,textRect = text_objects(msg,font)
         textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
         screen.blit(textSurf,textRect)

         if click[0]==1 and funct != None:
             time.sleep(0.15)

             if funct == "atacar":
                 ataque(seletor1,seletor2)

             if funct == "bordel":

                     bordel(seletor1)

             if funct == "mover":
                 if checker ==0:
                     checker = 1
                 else:
                     checker = 0
             if checker ==0:
                 if funct == "comprar10lan":
                     compra_lan(seletor1,10)
                 if funct == "comprar10esp":
                     compra_esp(seletor1,10)
                 if funct == "comprar10arq":
                     compra_arq(seletor1,10)
                 if funct == "comprar10cav":
                     compra_cav(seletor1,10)
                 if funct == "comprar10lobo":
                     compra_lobo(seletor1,10)
                 if funct == "comprar100lan":
                     compra_lan(seletor1,100)
                 if funct == "comprar100esp":
                     compra_esp(seletor1,100)
                 if funct == "comprar100arq":
                     compra_arq(seletor1,100)
                 if funct == "comprar100cav":
                     compra_cav(seletor1,100)
                 if funct == "comprar100lobo":
                     compra_lobo(seletor1,100)

    elif checker==0:
        pygame.draw.rect(screen,cori,(size[0],size[1],size[2],size[3]))
        textSurf,textRect = text_objects(msg,font)
        textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
        screen.blit(textSurf,textRect)


    elif size[0]+size[2] > mouse[0] > size[0] and size[1]+size[3] > mouse[1] > size[1]  and checker ==1:

             if funct=="atacar":
                 pygame.draw.rect(screen,cora,(size[0],size[1],size[2],size[3]))
                 textSurf,textRect = text_objects(msg,font)
                 textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
                 screen.blit(textSurf,textRect)
             else:

                 pygame.draw.rect(screen,greeng,(size[0],size[1],size[2],size[3]))
                 textSurf,textRect = text_objects(msg,font)
                 textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
                 screen.blit(textSurf,textRect)


             if click[0]==1:


                 time.sleep(0.15)
                 if funct == "atacar":
                     ataque(seletor1,seletor2)

                 if funct == "bordel":

                     bordel(seletor1)


                 if funct == "mover":
                     if checker ==0:
                         checker = 1
                     else:
                         checker = 0
                 if funct == "comprar10lan":
                     pygame.draw.rect(screen,green1,(size[0],size[1],size[2],size[3]))
                     textSurf,textRect = text_objects(msg,font)
                     textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
                     screen.blit(textSurf,textRect)

                     mover(seletor1,seletor2,"lan",10)
                 if funct == "comprar10esp":
                     pygame.draw.rect(screen,green1,(size[0],size[1],size[2],size[3]))
                     textSurf,textRect = text_objects(msg,font)
                     textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
                     screen.blit(textSurf,textRect)

                     mover(seletor1,seletor2,"esp",10)

                 if funct == "comprar10arq":
                     pygame.draw.rect(screen,green1,(size[0],size[1],size[2],size[3]))
                     textSurf,textRect = text_objects(msg,font)
                     textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
                     screen.blit(textSurf,textRect)

                     mover(seletor1,seletor2,"arq",10)

                 if funct == "comprar10cav":
                     pygame.draw.rect(screen,green1,(size[0],size[1],size[2],size[3]))
                     textSurf,textRect = text_objects(msg,font)
                     textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
                     screen.blit(textSurf,textRect)

                     mover(seletor1,seletor2,"cav",10)


                 if funct == "comprar10lobo":
                     pygame.draw.rect(screen,green1,(size[0],size[1],size[2],size[3]))
                     textSurf,textRect = text_objects(msg,font)
                     textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
                     screen.blit(textSurf,textRect)

                     mover(seletor1,seletor2,"lobo",10)

                 if funct == "comprar100lan":
                     pygame.draw.rect(screen,green1,(size[0],size[1],size[2],size[3]))
                     textSurf,textRect = text_objects(msg,font)
                     textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
                     screen.blit(textSurf,textRect)

                     mover(seletor1,seletor2,"lan",100)

                 if funct == "comprar100esp":
                     pygame.draw.rect(screen,green1,(size[0],size[1],size[2],size[3]))
                     textSurf,textRect = text_objects(msg,font)
                     textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
                     screen.blit(textSurf,textRect)

                     mover(seletor1,seletor2,"esp",100)

                 if funct == "comprar100arq":
                     pygame.draw.rect(screen,green1,(size[0],size[1],size[2],size[3]))
                     textSurf,textRect = text_objects(msg,font)
                     textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
                     screen.blit(textSurf,textRect)

                     mover(seletor1,seletor2,"arq",100)

                 if funct == "comprar100cav":
                     pygame.draw.rect(screen,green1,(size[0],size[1],size[2],size[3]))
                     textSurf,textRect = text_objects(msg,font)
                     textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
                     screen.blit(textSurf,textRect)

                     mover(seletor1,seletor2,"cav",100)

                 if funct == "comprar100lobo":
                     pygame.draw.rect(screen,green1,(size[0],size[1],size[2],size[3]))
                     textSurf,textRect = text_objects(msg,font)
                     textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
                     screen.blit(textSurf,textRect)

                     mover(seletor1,seletor2,"lobo",100)

                 if funct== "atacar" or funct== "mover":
                     pygame.draw.rect(screen,cori,(size[0],size[1],size[2],size[3]))
                     textSurf,textRect = text_objects(msg,font)
                     textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
                     screen.blit(textSurf,textRect)

    else:
        if funct=="atacar" or funct=="mover" or funct=="bordel":
            pygame.draw.rect(screen,cori,(size[0],size[1],size[2],size[3]))
            textSurf,textRect = text_objects(msg,font)
            textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
            screen.blit(textSurf,textRect)

        else:
            pygame.draw.rect(screen,green1,(size[0],size[1],size[2],size[3]))
            textSurf,textRect = text_objects(msg,font)
            textRect.center = ((size[0]+(size[2]/2)),(size[1]+(size[3]/2)))
            screen.blit(textSurf,textRect)



def slcd():
    global slc
    if slc ==0:

        slc =1
    else:
        slc=0

def circle(cori,cora,pos,rad,aldeian,aldeia):
    global seletor1
    global seletor2
    global slc

    cx = pos[0]
    cy = pos[1]
    dx = mouse[0]-cx
    dy = mouse[1]-cy
    distancec = math.sqrt(dx**2+dy**2)




    if distancec < rad:

        pygame.draw.circle(screen,cora,pos,rad,0)
        textSurf,textRect=text_objects(aldeian,font)
        textRect.center=(610,40)
        screen.blit(textSurf,textRect)
        mostra_tropas(aldeia)


        if click[0]==1:
            slcd()
            time.sleep(0.15)
            if slc == 0:
                seletor1 =aldeia





            else:
                seletor2 = aldeia






    else:
         pygame.draw.circle(screen,cori,pos,rad,0)




aliados = ['North']
inimigos = ['Iron_Islands','Vale','Riverlands','Crownlands','Stormlands',\
'Westerlands','The_Reach','Dorne']

class Aldeia(object):
    """Uma Aldeia """
    
    def __init__(self,nome,x,y,gold,income,lan,esp,arq,cav,lobo):
        
        self.nome = nome
        self.x = x
        self.y = y
        self.gold = gold
        self.income = income
        self.lan = lan
        self.esp = esp
        self.arq = arq
        self.cav = cav
        self.lobo = lobo
        self.forca_ataque = (self.lan*0.8 + self.esp*0.9 +\
        self.arq*1.2 + self.cav*1.3 + self.lobo)
        self.forca_defesa = (self.lan*0.9 + self.esp*0.92 +\
        self.arq*0.8 + self.cav*1.35 + self.lobo*0.7)

        

North = Aldeia("North","x","y",2000,200,200,140,105,10,12)  
Riverlands = Aldeia("Riverlands","x","y",3000,200,180,200,120,20,0)
Vale = Aldeia("Vale","x","y",9000,600,450,530,170,45,0)
Iron_Islands = Aldeia("Iron_Islands","x","y",3000,500,500,500,180,55,0)
Westerlands = Aldeia("Westerlands","x","y",5800,200,500,600,210,70,0)
Crownlands = Aldeia("Crownlands","x","y",240000,400,1200,1300,570,400,3)
Stormlands = Aldeia("Stormlands","x","y",15000,2000,600,630,200,110,0)
The_Reach = Aldeia("The_Reach","x","y",50000,200,650,650,210,190,0)
Dorne = Aldeia("Dorne","x","y",150000,200,800,720,250,250,0)


vilas_aliadas_objetos = [North]
vilas_inimigas_objetos = [Iron_Islands,Vale,Riverlands,Crownlands,Stormlands,\
Westerlands,The_Reach,Dorne]


def ataque (vila_ataca, vila_defende): 
    
    psegundo('Ataque Enviado',font2,3)

    if vila_ataca.nome in aliados and vila_defende.nome in aliados: 
        psegundo("Esta vila já é sua!",font2,3)
        
    elif vila_ataca.nome == "North" and vila_defende.nome != "Vale" \
    and vila_defende.nome != "Iron_Islands" and vila_defende.nome != "Riverlands":
        psegundo("Você não possui fronteira com essa vila",font2,3)
        
    elif vila_ataca.nome == "Riverlands" and vila_defende.nome != "Iron_Islands" \
    and vila_defende.nome != "Vale" and vila_defende.nome != "Crownlands"\
    and vila_defende.nome != "Westerlands":
        psegundo("Você não possui fronteira com essa vila",font2,3)
        
    elif vila_ataca.nome == "Vale" and vila_defende.nome != "North" \
    and vila_defende.nome != "Crownlands" and vila_defende.nome != "Riverlands":
        psegundo("Você não possui fronteira com essa vila",font2,3)
        
    elif vila_ataca.nome == "Westerlands" and vila_defende.nome != "Riverlands" \
    and vila_defende.nome != "Crownlands" and vila_defende.nome!="Iron_Islands"\
    and vila_defende.nome!="The_Reach":
        psegundo("Você não possui fronteira com essa vila",font2,3)
        
    elif vila_ataca.nome == "The_Reach" and vila_defende.nome != "Westerlands" \
    and vila_defende.nome != "Dorne" and vila_defende.nome != "Crownlands"\
    and vila_defende.nome!="Stormlands":
        psegundo("Você não possui fronteira com essa vila",font2,3)
        
    elif vila_ataca.nome == "Dorne" and vila_defende.nome != "The_Reach" \
    and vila_defende.nome != "Stormlands":
        psegundo("Você não possui fronteira com essa vila",font2,3)
    
    elif vila_ataca.nome == "Stormlands" and vila_defende.nome != "The_Reach" \
    and vila_defende.nome != "Dorne" and vila_defende.nome != "Crownlands":
        psegundo("Você não possui fronteira com essa vila",font2,3)
        
    elif vila_ataca.nome == "Iron_Islands" and vila_defende.nome != "North" \
    and vila_defende.nome != "Westerlands" and vila_defende.nome != "Riverlands":
        psegundo("Você não possui fronteira com essa vila",font2,3)
        
        
    elif vila_ataca.nome in aliados and vila_defende.nome in inimigos:
        
        forca_ataque = (vila_ataca.lan*0.8 + vila_ataca.esp*0.9 +\
        vila_ataca.arq*1.2 + vila_ataca.cav*1.3 + vila_ataca.lobo)*\
        (randint(60,100)/100)
        
        forca_defende = (vila_defende.lan*0.9 + vila_defende.esp*0.92 +\
        vila_ataca.arq*0.8 + vila_defende.cav*1.35 + vila_defende.lobo*0.7)*\
        (randint(70,110)/100)
        
        #p rint(forca_ataque, forca_defende)
        a =0
        a = time.time()
        while a < 5000:

            textSurf,textRect=text_objects(str(("A vila", vila_ataca.nome,"está atacando", vila_defende.nome)),font)
            textRect.center=(673,440)
            screen.blit(textSurf,textRect)


        
        if forca_ataque > forca_defende:
            
            vila_ataca.arq = int(vila_ataca.arq*(randint(50,80)/100))
            vila_ataca.cav = int(vila_ataca.cav*(randint(50,80)/100))
            vila_ataca.esp = int(vila_ataca.esp*(randint(50,80)/100))
            vila_ataca.lan = int(vila_ataca.lan*(randint(50,80)/100))
            vila_ataca.lobo = int(vila_ataca.lobo*(randint(40,80)/100))
            
            vila_defende.arq = int(vila_defende.arq*(randint(0,30)/100))
            vila_defende.cav = int(vila_defende.cav*(randint(0,30)/100))
            vila_defende.esp = int(vila_defende.esp*(randint(0,30)/100))
            vila_defende.lan = int(vila_defende.lan*(randint(0,30)/100))
            vila_defende.lobo = int(vila_defende.lobo*(randint(0,30)/100)) 
            
            if vila_defende.nome in inimigos:
                inimigos.remove(vila_defende.nome)
                aliados.append(vila_defende.nome)
                vilas_aliadas_objetos.append(vila_defende) 
                vilas_inimigas_objetos.remove(vila_defende)
                
            if vila_defende.nome in aliados and vila_ataca.nome in inimigos:
                aliados.remove(vila_defende.nome)
                inimigos.append(vila_defende.nome)
                vilas_aliadas_objetos.remove(vila_defende)
                vilas_inimigas_objetos.append (vila_defende)
            
            #chamar funcao dos bonequinhos lutando nesse ponto
            time.sleep(3)
                
            psegundo("Ataque Vitorioso!",font1,3)

        
        if forca_defende > forca_ataque:
            
            vila_ataca.arq = int(vila_ataca.arq*(randint(0,15)/100))
            vila_ataca.cav = int(vila_ataca.cav*(randint(0,10)/100))
            vila_ataca.esp = int(vila_ataca.esp*(randint(0,15)/100))
            vila_ataca.lan = int(vila_ataca.lan*(randint(0,20)/100))
            vila_ataca.lobo = int(vila_ataca.lobo*(randint(0,20)/100))
        
            vila_defende.arq = int(vila_defende.arq*(randint(50,80)/100))
            vila_defende.cav = int(vila_defende.cav*(randint(50,80)/100))
            vila_defende.esp = int(vila_defende.esp*(randint(50,80)/100))
            vila_defende.lan = int(vila_defende.lan*(randint(50,80)/100))
            vila_defende.lobo = int(vila_defende.lobo*(randint(40,80)/100))
            
            #chamar funcao dos bonequinhos lutando nesse ponto
            time.sleep(3)
            
            psegundo("Voce perdeu a Batalha!",font1,3)

            

def mover(vila_sai,vila_chega,tro,q):
    
    if vila_sai.nome in aliados and vila_chega.nome in aliados:
        
            
        if tro == "lan":
            if q>vila_sai.lan:
                q = 0
                psegundo("Você não possui tantas tropas",font3,3)
            (vila_sai.lan) = int(vila_sai.lan) - int(q)
            (vila_chega.lan)=int(vila_chega.lan)+int(q*(randint(87,100)/100))

        if tro == "esp":
            if q>vila_sai.esp:
                q = 0
                psegundo("Você não possui tantas tropas",font3,3)
            (vila_sai.esp) = int(vila_sai.esp) - int(q)
            (vila_chega.esp)=int(vila_chega.esp)+int(q*(randint(87,100)/100))

        if tro == "arq":
            if q>vila_sai.arq:
                q = 0
                psegundo("Você não possui tantas tropas",font3,3)
            (vila_sai.arq) = int(vila_sai.arq) - int(q)
            (vila_chega.arq)=int(vila_chega.arq)+int(q*(randint(87,100)/100))

        if tro == "cav":
            if q>vila_sai.cav:
                q = 0
                psegundo("Você não possui tantas tropas",font3,3)
            (vila_sai.cav) = int(vila_sai.cav) - int(q)
            (vila_chega.cav)=int(vila_chega.cav)+int(q*(randint(87,100)/100))

        if tro == "lobo":
            if q>vila_sai.lobo:
                q = 0
                psegundo("Você não possui tantas tropas",font3,3)
            vila_sai.lobo = int(vila_sai.lobo) - int(q)

            (vila_chega.lobo)=int(vila_chega.lobo)+int(q*(randint(87,100)/100))

        
        psegundo("Tropas Enviadas",font2,3)
        
    else:
        psegundo("Você não pode mover tropas para essa vila",font3,3)
        

        
        
    
def compra_arq(vila_dinheiro,quantidade):
    
    preco_arq = 100
    numero = quantidade
    
    total_gasto = preco_arq*numero
    
    if total_gasto > vila_dinheiro.gold:
        total_gasto = 0
        numero =0

        textSurf,textRect=text_objects('Gold Insuficiente',font2)
        textRect.center=(750,550)
        screen.blit(textSurf,textRect)
    else:
        textSurf,textRect=text_objects('Tropas Compradas',font2)
        textRect.center=(750,550)
        screen.blit(textSurf,textRect)
        
    vila_dinheiro.gold = vila_dinheiro.gold - total_gasto
    vila_dinheiro.arq = int(vila_dinheiro.arq) + numero



def bordel(vila):
    qntganha =200
    total_gasto = 1000
    if total_gasto > vila.gold:
        total_gasto = 0
        qntganha =0
        psegundo('Gold Insuficiente',font2,3)

    psegundo('Tropas Compradas',font2,3)
    vila.gold = vila.gold - total_gasto
    vila.income = int(vila.income) + qntganha


    psegundo('Bordel Comprado',font2,3)


def compra_cav(vila_dinheiro,quantidade):
    
    preco_cav = 150
    numero = quantidade

    
    total_gasto = preco_cav*numero
    
    if total_gasto > vila_dinheiro.gold:
        total_gasto = 0
        numero=0

        psegundo('Gold Insuficiente',font2,3)
    else:
        psegundo('Tropas Compradas',font2,3)


    vila_dinheiro.gold = vila_dinheiro.gold - total_gasto
    vila_dinheiro.cav = int(vila_dinheiro.cav) + numero




    
def compra_esp(vila_dinheiro,quantidade):
    
    preco_esp = 45
    numero = quantidade
    
    total_gasto = preco_esp*numero
    
    if total_gasto > vila_dinheiro.gold:
        total_gasto = 0
        numero=0

        psegundo('Gold Insuficiente',font2,3)

    else:
        psegundo('Tropas Compradas',font2,3)

    vila_dinheiro.gold = vila_dinheiro.gold - total_gasto
    vila_dinheiro.esp = int(vila_dinheiro.esp) + numero

    
def compra_lan(vila_dinheiro,quantidade):

    
    preco_lan = 15
    numero = quantidade
    
    total_gasto = preco_lan*numero
    
    if total_gasto > vila_dinheiro.gold:
        total_gasto = 0
        numero=0

        psegundo('Gold Insuficiente',font2,3)
    else:
        psegundo('Tropas Compradas',font2,3)

    vila_dinheiro.gold = vila_dinheiro.gold - total_gasto
    vila_dinheiro.lan = int(vila_dinheiro.lan) + numero



    
def compra_lobo(vila_dinheiro,quantidade):
    
    preco_lobo = 175
    numero = quantidade
    
    total_gasto = preco_lobo*numero
    
    if total_gasto > vila_dinheiro.gold:
        total_gasto = 0
        numero=0

        psegundo('Gold Insuficiente',font2,3)

    else:
        psegundo('Tropas Compradas',font2,3)
    vila_dinheiro.gold = vila_dinheiro.gold - total_gasto
    vila_dinheiro.lobo = int(vila_dinheiro.lobo) + numero


    
def estado_vila(vila): 
            
    if vila.nome in aliados:
        
        if vila.forca_defesa < (500)*(randint(110,220)/100):
            #precisa arrumar a forca para cada vila quando as tropas iniciais
            #estuverem definidas
            print ("A vila",vila.nome,"está fraca!\
            Lembre-se de defender todas as suas vilas")
        
        return "Ouro:", vila.gold, "Arqueiros:" , vila.arq,\
        "Cavaleiros:", vila.cav,"Lanceiros:", vila.lan, "Lobos:" , vila.lobo,\
        "Força de Defesa", vila.forca_defesa
    
    if vila.nome in inimigos: 
        
         pass
        
        
def tempo():
    

        
        for vila in vilas_aliadas_objetos:
            vila.gold = int(vila.gold)+ int(vila.income)
        


        for vila in vilas_inimigas_objetos:
            
            vila.arq += 1
            vila.esp += 1
            vila.cav += 1
            vila.lan += 2
            vila.lobo += 1



    
def ataque_inimigo():
    
    lista_ataca_North = [] 
    lista_ataca_Riverlands = [] 
    lista_ataca_Westerlands = []
    lista_ataca_The_Reach = []
    lista_ataca_Stormlands = []
    lista_ataca_Dorne = []
    lista_ataca_Vale = []
    lista_ataca_Iron_Islands = []
    #lista_ataca_Crownlands = []
    
    for vila in vilas_aliadas_objetos:
      
        if vila.nome == "North" and \
        vila.forca_defesa<(500)*(randint(110,220)/100):
        
            if 'Vale' in inimigos and Vale.forca_ataque >= \
            North.forca_defesa:
                lista_ataca_North.append(Vale)
                
            if 'Riverlands' in inimigos and Riverlands.forca_ataque >= \
            North.forca_defesa:
                lista_ataca_North.append(Riverlands)
                
            if 'Iron_Islands' in inimigos and Iron_Islands.forca_ataque >= \
            North.forca_defesa:
                lista_ataca_North.append(Iron_Islands)       
                
            if len (lista_ataca_North) != 0:
                ataque(lista_ataca_North[randint(0,len(lista_ataca_North)-1)],North)
                
                #time.sleep(10000)
        
        if vila.nome == "Riverlands" and \
    vila.forca_defesa<(600)*(randint(110,220)/100):

            if 'Crownlands' in inimigos and Crownlands.forca_ataque >= \
            Riverlands.forca_defesa:
                lista_ataca_Riverlands.append(Crownlands)
                
            if 'Westerlands' in inimigos and Westerlands.forca_ataque >= \
            Riverlands.forca_defesa:
                lista_ataca_Riverlands.append(Westerlands)
                
            if 'Iron_Islands' in inimigos and Iron_Islands.forca_ataque >= \
            Riverlands.forca_defesa:
                lista_ataca_Riverlands.append(Iron_Islands)
                
            if 'Vale' in inimigos and Vale.forca_ataque >= \
            Riverlands.forca_defesa:
                lista_ataca_Riverlands.append(Vale)
            
            if len (lista_ataca_Riverlands) != 0:
                ataque(lista_ataca_Riverlands[randint(0,len(lista_ataca_Riverlands)-1)],Riverlands)
                
                #time.sleep(10000)
            
        if vila.nome == "Vale" and \
    vila.forca_defesa<(700)*(randint(110,220)/100):
        
            if 'North' in inimigos and North.forca_ataque >= \
            Vale.forca_defesa:
                  lista_ataca_Vale.append(Crownlands)
        
            if 'Riverlands' in inimigos and Riverlands.forca_ataque >= \
            Vale.forca_defesa:
                  lista_ataca_Vale.append(Riverlands)
                  
            if 'Crownlands' in inimigos and Crownlands.forca_ataque >= \
            Vale.forca_defesa:
                  lista_ataca_Vale.append(Crownlands)
                  
            if len (lista_ataca_Vale) != 0:
                ataque(lista_ataca_Vale[randint(0,len(lista_ataca_Vale)-1)],Vale)
                
                #time.sleep(10000)                
                
        if vila.nome == "Iron_Islands" and \
    vila.forca_defesa<(700)*(randint(110,220)/100):
            
            if 'Westerlands' in inimigos and Westerlands.forca_ataque >= \
                Iron_Islands.forca_defesa:
                      lista_ataca_Iron_Islands.append(Westerlands)
                      
            if 'Riverlands' in inimigos and Riverlands.forca_ataque >= \
                Iron_Islands.forca_defesa:
                      lista_ataca_Iron_Islands.append(Riverlands)
                      
            if 'North' in inimigos and North.forca_ataque >= \
                North.forca_defesa:
                      lista_ataca_Iron_Islands.append(Crownlands)
        
            if len (lista_ataca_Iron_Islands) != 0:
                ataque(lista_ataca_Iron_Islands\
                [randint(0,len(lista_ataca_Iron_Islands)-1)],Iron_Islands)
                
                #time.sleep(10000)
                  
        if vila.nome == "Westerlands" and \
    vila.forca_defesa<(800)*(randint(110,220)/100):
        
            if 'Riverlands' in inimigos and Riverlands.forca_ataque >= \
            Westerlands.forca_defesa:
                  lista_ataca_Westerlands.append(Riverlands)
                  
            if 'Crownlands' in inimigos and Crownlands.forca_ataque >= \
            Westerlands.forca_defesa:
                  lista_ataca_Westerlands.append(Crownlands)
                  
            if 'The_Reach' in inimigos and The_Reach.forca_ataque >= \
            Westerlands.forca_defesa:
                  lista_ataca_Westerlands.append(The_Reach)
                  
            if 'Iron_Islands' in inimigos and Iron_Islands.forca_ataque >= \
            Westerlands.forca_defesa:
                  lista_ataca_Westerlands.append(Iron_Islands)

            if len (lista_ataca_Westerlands) != 0:
                ataque(lista_ataca_Westerlands[randint(0,len(lista_ataca_Westerlands)-1)],Westerlands)
                
                #time.sleep(10000)
        
        if vila.nome == "The_Reach" and \
    vila.forca_defesa<(900)*(randint(110,220)/100):
            
            if 'Westerlands' in inimigos and Westerlands.forca_ataque >= \
            The_Reach.forca_defesa:
                  lista_ataca_The_Reach.append(Westerlands)
                  
            if 'Dorne' in inimigos and Dorne.forca_ataque >= \
            The_Reach.forca_defesa:
                  lista_ataca_The_Reach.append(Dorne)
                  
            if 'Stormlands' in inimigos and Stormlands.forca_ataque >= \
            The_Reach.forca_defesa:
                  lista_ataca_The_Reach.append(Stormlands)
                  
            if 'Crownlands' in inimigos and Crownlands.forca_ataque >= \
            The_Reach.forca_defesa:
                  lista_ataca_The_Reach.append(Crownlands)
                  
            if len (lista_ataca_The_Reach) != 0:
                ataque(lista_ataca_The_Reach[randint(0,len(lista_ataca_The_Reach)-1)],The_Reach)
               
               # time.sleep(10000)
            
        if vila.nome == "Dorne" and \
    vila.forca_defesa<(900)*(randint(110,220)/100):
        
            if 'The_Reach' in inimigos and The_Reach.forca_ataque >= \
                Dorne.forca_defesa:
                      lista_ataca_Dorne.append(The_Reach)
                      
            if 'Stormlands' in inimigos and Stormlands.forca_ataque >= \
                Dorne.forca_defesa:
                      lista_ataca_Dorne.append(Stormlands)
            
            if len (lista_ataca_Dorne) != 0:
                ataque(lista_ataca_Dorne[randint(0,len(lista_ataca_Dorne)-1)],Dorne)
                
                #time.sleep(10000) 
            
        if vila.nome == "Stormlands" and \
    vila.forca_defesa<(970)*(randint(110,220)/100):
            
            if 'The_Reach' in inimigos and The_Reach.forca_ataque >= \
                Stormlands.forca_defesa:
                      lista_ataca_Stormlands.append(The_Reach)
                      
            if 'Dorne' in inimigos and Dorne.forca_ataque >= \
                Stormlands.forca_defesa:
                      lista_ataca_Stormlands.append(Dorne)
                      
            if 'Crownlands' in inimigos and Crownlands.forca_ataque >= \
                Stormlands.forca_defesa:
                      lista_ataca_Stormlands.append(Crownlands)
        
            if len (lista_ataca_Stormlands) != 0:
                ataque(lista_ataca_Stormlands[randint(0,len(lista_ataca_Stormlands)-1)],Stormlands)
                
                #time.sleep(10000)

seletor1=nada
seletor2=nada
contador = 0
#####################################
size = (x, y)
screen = pygame.display.set_mode(size)

pygame.display.set_caption("Game of Thrones The Game")
clock = pygame.time.Clock()
pygame.mixer.music.load("got.mp3")
pygame.mixer.music.play(-1)

defeated = False
victory = False
while not defeated and not victory:

     ttim = Timer(1800,ataque_inimigo())
     ttim.start()



     for event in pygame.event.get():



         background = pygame.image.load("foto2.jpg")

         backgroundRect = background.get_rect()
         screen.blit(background, backgroundRect)

         font= pygame.font.Font("freesansbold.ttf",35)
         font1= pygame.font.Font("freesansbold.ttf",25)
         font2= pygame.font.Font("freesansbold.ttf",25)
         font3= pygame.font.Font("freesansbold.ttf",15)
         font4= pygame.font.Font("freesansbold.ttf",20)


         mouse= pygame.mouse.get_pos()
         click = pygame.mouse.get_pressed()

         pygame.draw.rect(screen,ggrey,(500,0,1080,300))
         pygame.draw.rect(screen,tan1,(500,300,1080,800))

         textSurf,textRect=text_objects('Origem:',font)
         textRect.center=(570,100)
         screen.blit(textSurf,textRect)
         textSurf,textRect=text_objects('Destino:',font)
         textRect.center=(570,150)
         screen.blit(textSurf,textRect)

         textSurf,textRect=text_objects('Lanceiros:',font)
         textRect.center=(642,810)
         screen.blit(textSurf,textRect)
         textSurf,textRect=text_objects('Espadachins:',font)
         textRect.center=(615,860)
         screen.blit(textSurf,textRect)
         textSurf,textRect=text_objects('Arqueiros:',font)
         textRect.center=(640,910)
         screen.blit(textSurf,textRect)
         textSurf,textRect=text_objects('Cavalaria:',font)
         textRect.center=(642,960)
         screen.blit(textSurf,textRect)
         textSurf,textRect=text_objects('Lobos:',font)
         textRect.center=(673,1000)
         screen.blit(textSurf,textRect)










         Northc = circle(Northcor,black,(250,230),50,"The North",North)
         Riverlandsc = circle(Riverlandscor,black,(250,550),30,"Riverlands",Riverlands)
         Westerlandsc = circle(Westerlandscor,black,(155, 632),25,"Westerlands",Westerlands)
         The_Reachc = circle(The_Reachcor,black,(190,735),35,"The Reach",The_Reach)
         Stormlandsc = circle(Stormlandscor,black,(365, 795),25,"Stormlands",Stormlands)
         Dornec = circle(Dornecor,black,(250,900),40,"Dorne",Dorne)
         Valec = circle(Valecor,black,(374, 524),35,"Vale",Vale)
         Iron_Islandsc = circle(Iron_Islandscor,black,(100, 514),15,"Iron Islands",Iron_Islands)
         Crownlandsc= circle(Crownlandscor,black,(362, 659),30,"Crownlands",Crownlands)

         seletor1 =seletor1
         seletor2 =seletor2

         textSurf1,textRect1=text_objects(seletor1.nome,font)
         textRect1.center=(800,100)
         screen.blit(textSurf1,textRect1)
         textSurf,textRect=text_objects(seletor2.nome,font)
         textRect.center=(800,150)
         screen.blit(textSurf,textRect)
         fontg=pygame.font.Font("freesansbold.ttf",50)

         textSurf,textRect=text_objects('Gold:',font)
         textRect.center=(812,25)
         screen.blit(textSurf,textRect)
         textSurf,textRect=text_objects('Income:',font)
         textRect.center=(790,50)
         screen.blit(textSurf,textRect)
         textSurf,textRect=text_objects('Lanceiros:',font)
         textRect.center=(642,320)
         screen.blit(textSurf,textRect)
         textSurf,textRect=text_objects('Espadachins:',font)
         textRect.center=(615,350)
         screen.blit(textSurf,textRect)
         textSurf,textRect=text_objects('Arqueiros:',font)
         textRect.center=(640,380)
         screen.blit(textSurf,textRect)
         textSurf,textRect=text_objects('Cavalaria:',font)
         textRect.center=(642,410)
         screen.blit(textSurf,textRect)
         textSurf,textRect=text_objects('Lobos:',font)
         textRect.center=(673,440)
         screen.blit(textSurf,textRect)

         if  checker == 1:
             textSurf,textRect=text_objects('Mover',fontg)
             textRect.center=(730,740)
             screen.blit(textSurf,textRect)
         else:
             textSurf,textRect=text_objects('Comprar',fontg)
             textRect.center=(730,740)
             screen.blit(textSurf,textRect)

        ## textSurf,textRect=text_objects(str(time.time()),fontg)
        # textRect.center=(200,200)
       # screen.blit(textSurf,textRect)
         but("10",font,(760,790,60,40),red,red1,"comprar10lan")
         but("10",font,(760,840,60,40),red,red1,"comprar10esp")
         but("10",font,(760,890,60,40),red,red1,"comprar10arq")
         but("10",font,(760,940,60,40),red,red1,"comprar10cav")
         but("10",font,(760,990,60,40),red,red1,"comprar10lobo")
         but("100",font,(860,790,60,40),red,red1,"comprar100lan")
         but("100",font,(860,840,60,40),red,red1,"comprar100esp")
         but("100",font,(860,890,60,40),red,red1,"comprar100arq")
         but("100",font,(860,940,60,40),red,red1,"comprar100cav")
         but("100",font,(860,990,60,40),red,red1,"comprar100lobo")






         but("MOVER/COMPRAR",font3,(550,200,150,85),green,green1,"mover")
         but("ATACAR",font,(780,200,150,85),red,red1,"atacar")
         but("COMPRAR BORDEL",font2,(620,600,280,85),red,red1,"bordel")


         if event.type == pygame.QUIT:

             sys.exit()




         pygame.display.update()
         clock.tick(60)

         if time.time()-contador > 300:
             tempo()
             contador =time.time()




pygame.quit()


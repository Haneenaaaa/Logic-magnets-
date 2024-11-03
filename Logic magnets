from gzip import READ
import pygame
import random
import sys
pygame.init()


width = 800
height = 600

screen = pygame.display.set_mode((width, height))
RED = (255, 0, 0)
BLUE = (0, 0, 255)
IRON_COLOR = (169, 169, 169)
WHITE=(255,255,255)
BLACKE=(0,0,0)
gravity = 0.05
force = gravity 


background_color = (0, 255, 255) 
gaps = [[60,380],[320,360],[570,360],[60,90]]

magnets = [[100, 210, 'red'], [700, 400, 'blue'], [100, 500, 'iron'],[600,400,'iron']]
move_speed = 1
def draw_gaps():
    for gap in gaps: 
         pygame.draw.rect(screen, WHITE, (gap[0], gap[1],80,80), 3)

def draw_magnets():
     for magnet in magnets:
        color = RED if magnet[2] == 'red' else BLUE if magnet[2] == 'blue' else IRON_COLOR
        pygame.draw.circle(screen, color, (magnet[0], magnet[1]), 30)
        
    

def  magnet  (index, dx, dy): 
        
        if magnets[0][1]==magnets[2][1]  :
          # x, y, color = magnets[2]
         #  magnets[2] = (x + dx * move_speed,  y* move_speed, color) 
            move_magnet(2, 0, -0.2)
        elif   magnets[0][0]==magnets[2][0] :
                #  x, y, color = magnets[2]
                #  magnets[2] = (x  * move_speed,  y + dy * move_speed, color) 
                   move_magnet(2, 0, -0.2)
 
    
    

def  move_magnet  (index, dx, dy): 
    x, y, color = magnets[index]
    magnets[index] = (x + dx * move_speed, y + dy * move_speed, color) 
#     if magnets[0]==gaps[0]  :
#          move_magnet(2, -0.2, 0)
     
   
def movblue():
        if magnets[1][1]==magnets[3][1]:
                move_magnet(3, -0.2, 0) 








running = True
while True:
   
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
              pygame.quit()
              sys.exit()
   
    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT]:
            move_magnet(1, -0.1, 0)
            movblue() 
           # magnet(2, 0.1, 0)
    if keys[pygame.K_RIGHT]:
            move_magnet(1, 0.1, 0) 
          #  magnet(2, -0.1, 0)
    if keys[pygame.K_UP]:
            move_magnet(0, 0, -0.1)
           # magnet(2, 0, 0.1)
    if keys[pygame.K_DOWN]:
            move_magnet(0, 0, 0.1)
            magnet(2, 0, -0.1)
    

    screen.fill((128, 0, 128))
    draw_gaps()
    draw_magnets()
    pygame.display.flip()
#     if magnets[0]==gaps[3]:
#          pygame.WINDOWCLOSE()

pygame.quit()

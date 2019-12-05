import pygame
import sys
import time
from pygame.locals import *
from random import randint

pygame.init()

WINDOW_WIDTH = 1024
WINDOW_HEIGHT = 600

clock = pygame.time.Clock()

player1_win = False
player2_win = False

UP1 = False
DOWN1 = False
NO_MOVEMENT1 = True

UP2 = False
DOWN2 = False
NO_MOVEMENT2 = True

UPLEFT = 0
DOWNLEFT = 1
UPRIGHT = 2
DOWNRIGHT = 3

default_ball_speed = 4

orange = (255, 180, 0)
red = (255, 0, 0)
blue = (0, 25, 255)
green = (0, 255, 0)
purple = (128, 0, 128)
yellow = (255, 255, 0)
white = (255, 255, 255)
black = (0, 0, 0)

main_surface = pygame.display.set_mode((WINDOW_WIDTH, WINDOW_HEIGHT), 0, 32)
pygame.display.set_caption('Ping-Pong')
surface_rect = main_surface.get_rect()


def change_bg_color_default():
    global black
    black = (0, 0, 0)


def change_bg_color_blue():
    global black
    black = blue


def change_bg_color_red():
    global black
    black = red


def change_bg_color_green():
    global black
    black = green


def change_bg_color_orange():
    global black
    black = orange


def change_bg_color_pink():
    global black
    black = purple


def change_bg_color_yellow():
    global black
    black = yellow


class MenuRackets:
    def __init__(self, punkts_4=[150, 140, 'Punkt', (250, 250, 30), (250, 30, 250), 0]):
        self.punkts_4 = punkts_4

    def render(self, powerh, font, num_pnkt):
        for i in self.punkts_4:
            if num_pnkt == i[5]:
                powerh.blit(font.render(i[2], 1, i[4]), (i[0], i[1] - 30))
            else:
                powerh.blit(font.render(i[2], 1, i[3]), (i[0], i[1] - 30))

    def menu(self):
        global black
        global white
        window = pygame.Surface((1024, 600))
        pygame.key.set_repeat(0, 0)
        pygame.mouse.set_visible(True)
        done = True
        font_menu = pygame.font.SysFont('Arial', 50)
        punkt = 0
        while done:
            mm = pygame.mouse.get_pos()
            for i in self.punkts_4:
                if mm[0] > i[0] and mm[0] < i[0] + 155 and mm[1] > i[1] and mm[1] < i[1] + 50:
                    punkt = i[5]
            self.render(window, font_menu, punkt)
            for e in pygame.event.get():
                if e.type == pygame.QUIT:
                    sys.exit()
                if e.type == pygame.KEYDOWN:
                    if e.key == pygame.K_ESCAPE:
                        done = False
                    if e.key == pygame.K_UP:
                        if punkt == 0:
                            punkt = len(self.punkts_4)
                        if punkt > 0:
                            punkt -= 1
                    if e.key == pygame.K_DOWN:
                        if punkt == 20:
                            punkt = (len(self.punkts_4)) - (len(self.punkts_4) + 1)
                        if punkt < len(self.punkts_4) - 1:
                            punkt += 1
                    if e.key == pygame.K_RETURN:
                        if punkt == 0:
                            racket1.change_color_default()
                            racket2.change_color_default()
                        elif punkt == 1:
                            racket1.change_color_blue()
                            racket2.change_color_blue()
                        elif punkt == 2:
                            racket1.change_color_red()
                            racket2.change_color_red()
                        elif punkt == 3:
                            racket1.change_color_green()
                            racket2.change_color_green()
                        elif punkt == 4:
                            racket1.change_color_orange()
                            racket2.change_color_orange()
                        elif punkt == 5:
                            racket1.change_color_pink()
                            racket2.change_color_pink()
                        elif punkt == 6:
                            racket1.change_color_yellow()
                            racket2.change_color_yellow()
                        elif punkt == 7:
                            racket1.change_speed_default()
                            racket2.change_speed_default()
                        elif punkt == 8:
                            racket1.change_speed_10()
                            racket2.change_speed_10()
                        elif punkt == 9:
                            racket1.change_speed_12()
                            racket2.change_speed_12()
                        elif punkt == 10:
                            racket1.change_speed_14()
                            racket2.change_speed_14()
                        elif punkt == 11:
                            racket1.change_speed_16()
                            racket2.change_speed_16()
                        elif punkt == 12:
                            racket1.change_speed_18()
                            racket2.change_speed_18()
                        elif punkt == 13:
                            racket1.change_speed_18()
                            racket2.change_speed_18()
                        elif punkt == 14:
                            racket1.change_size_default()
                            racket2.change_size_default()
                        elif punkt == 15:
                            racket1.change_size_3()
                            racket2.change_size_3()
                        elif punkt == 16:
                            racket1.change_size_5()
                            racket2.change_size_5()
                        elif punkt == 17:
                            racket1.change_size_15()
                            racket2.change_size_15()
                        elif punkt == 18:
                            racket1.change_size_20()
                            racket2.change_size_20()

                if e.type == pygame.MOUSEBUTTONDOWN and e.button == 1:
                    if punkt == 0:
                        racket1.change_color_default()
                        racket2.change_color_default()
                    elif punkt == 1:
                        racket1.change_color_blue()
                        racket2.change_color_blue()
                    elif punkt == 2:
                        racket1.change_color_red()
                        racket2.change_color_red()
                    elif punkt == 3:
                        racket1.change_color_green()
                        racket2.change_color_green()
                    elif punkt == 4:
                        racket1.change_color_orange()
                        racket2.change_color_orange()
                    elif punkt == 5:
                        racket1.change_color_pink()
                        racket2.change_color_pink()
                    elif punkt == 6:
                        racket1.change_color_yellow()
                        racket2.change_color_yellow()
                    elif punkt == 7:
                        racket1.change_speed_default()
                        racket2.change_speed_default()
                    elif punkt == 8:
                        racket1.change_speed_10()
                        racket2.change_speed_10()
                    elif punkt == 9:
                        racket1.change_speed_12()
                        racket2.change_speed_12()
                    elif punkt == 10:
                        racket1.change_speed_14()
                        racket2.change_speed_14()
                    elif punkt == 11:
                        racket1.change_speed_16()
                        racket2.change_speed_16()
                    elif punkt == 12:
                        racket1.change_speed_18()
                        racket2.change_speed_18()
                    elif punkt == 13:
                        racket1.change_speed_18()
                        racket2.change_speed_18()
                    elif punkt == 14:
                        racket1.change_size_default()
                        racket2.change_size_default()
                    elif punkt == 15:
                        racket1.change_size_3()
                        racket2.change_size_3()
                    elif punkt == 16:
                        racket1.change_size_5()
                        racket2.change_size_5()
                    elif punkt == 17:
                        racket1.change_size_15()
                        racket2.change_size_15()
                    elif punkt == 18:
                        racket1.change_size_20()
                        racket2.change_size_20()

            window.blit(font_menu.render('Rackets color', 1, (0, 255, 120)), (40, 20))
            window.blit(font_menu.render('Rackets speed', 1, (0, 255, 120)), (400, 20))
            window.blit(font_menu.render('Rackets size', 1, (0, 255, 120)), (770, 20))
            main_surface.blit(window, (0, 0))
            window.fill((0, 0, 0))
            pygame.display.flip()


punkts_4 = [(50, 130, 'Default', (255, 180, 0), (255, 255, 255), 0),
            (50, 200, 'Blue', (255, 180, 0), (0, 25, 255), 1),
            (50, 270, 'Red', (255, 180, 0), (255, 0, 0), 2),
            (50, 340, 'Green', (255, 180, 0), (0, 255, 0), 3),
            (50, 410, 'Orange', (255, 180, 0), (255, 255, 255), 4),
            (50, 480, 'Purple', (255, 180, 0), (128, 0, 128), 5),
            (50, 550, 'Yellow', (255, 180, 0), (255, 255, 0), 6),
            (400, 130, 'Default', (255, 180, 0), (0, 150, 250), 7),
            (400, 200, '10', (255, 180, 0), (0, 150, 250), 8),
            (400, 270, '12', (255, 180, 0), (0, 150, 250), 9),
            (400, 340, '14', (255, 180, 0), (0, 150, 250), 10),
            (400, 410, '16', (255, 180, 0), (0, 150, 250), 11),
            (400, 480, '18', (255, 180, 0), (0, 150, 250), 12),
            (400, 550, '20', (255, 180, 0), (0, 150, 250), 13),
            (800, 130, 'Default(10)', (255, 180, 0), (0, 150, 250), 14),
            (800, 200, '3', (255, 180, 0), (0, 150, 250), 15),
            (800, 270, '5', (255, 180, 0), (0, 150, 250), 16),
            (800, 340, '15', (255, 180, 0), (0, 150, 250), 17),
            (800, 410, '20', (255, 180, 0), (0, 150, 250), 18)]

menu_rackets_settings = MenuRackets(punkts_4)


class MenuBall:
    def __init__(self, punkts_3=[150, 140, 'Punkt', (250, 250, 30), (250, 30, 250), 0]):
        self.punkts_3 = punkts_3

    def render(self, powerh, font, num_pnkt):
        for i in self.punkts_3:
            if num_pnkt == i[5]:
                powerh.blit(font.render(i[2], 1, i[4]), (i[0], i[1] - 30))
            else:
                powerh.blit(font.render(i[2], 1, i[3]), (i[0], i[1] - 30))

    def menu(self):
        global default_ball_speed
        global black
        global white
        window = pygame.Surface((1024, 600))
        pygame.key.set_repeat(0, 0)
        pygame.mouse.set_visible(True)
        done = True
        font_menu = pygame.font.SysFont('Arial', 50)
        punkt = 0
        while done:
            mm = pygame.mouse.get_pos()
            for i in self.punkts_3:
                if mm[0] > i[0] and mm[0] < i[0] + 155 and mm[1] > i[1] and mm[1] < i[1] + 50:
                    punkt = i[5]
            self.render(window, font_menu, punkt)
            for e in pygame.event.get():
                if e.type == pygame.QUIT:
                    sys.exit()
                if e.type == pygame.KEYDOWN:
                    if e.key == pygame.K_ESCAPE:
                        done = False
                    if e.key == pygame.K_UP:
                        if punkt == 0:
                            punkt = len(self.punkts_3)
                        if punkt > 0:
                            punkt -= 1
                    if e.key == pygame.K_DOWN:
                        if punkt == 20:
                            punkt = (len(self.punkts_3)) - (len(self.punkts_3) + 1)
                        if punkt < len(self.punkts_3) - 1:
                            punkt += 1
                    if e.key == pygame.K_RETURN:
                        if punkt == 0:
                            ball.change_color_default()
                        elif punkt == 1:
                            ball.change_color_blue()
                        elif punkt == 2:
                            ball.change_color_red()
                        elif punkt == 3:
                            ball.change_color_green()
                        elif punkt == 4:
                            ball.change_color_orange()
                        elif punkt == 5:
                            ball.change_color_pink()
                        elif punkt == 6:
                            ball.change_color_yellow()
                        elif punkt == 7:
                            ball.change_speed_default()
                            default_ball_speed = 4
                        elif punkt == 8:
                            ball.change_speed_10()
                            default_ball_speed = 10
                        elif punkt == 9:
                            ball.change_speed_12()
                            default_ball_speed = 12
                        elif punkt == 10:
                            ball.change_speed_14()
                            default_ball_speed = 14
                        elif punkt == 11:
                            ball.change_speed_16()
                            default_ball_speed = 16
                        elif punkt == 12:
                            ball.change_speed_18()
                            default_ball_speed = 18
                        elif punkt == 13:
                            ball.change_speed_20()
                            default_ball_speed = 20
                        elif punkt == 14:
                            ball.change_size_default()
                        elif punkt == 15:
                            ball.change_size_20()
                        elif punkt == 16:
                            ball.change_size_30()
                        elif punkt == 17:
                            ball.change_size_40()
                        elif punkt == 18:
                            ball.change_size_50()
                        elif punkt == 19:
                            ball.change_size_60()
                        elif punkt == 20:
                            ball.change_size_70()

                if e.type == pygame.MOUSEBUTTONDOWN and e.button == 1:
                    if punkt == 0:
                        ball.change_color_default()
                    elif punkt == 1:
                        ball.change_color_blue()
                    elif punkt == 2:
                        ball.change_color_red()
                    elif punkt == 3:
                        ball.change_color_green()
                    elif punkt == 4:
                        ball.change_color_orange()
                    elif punkt == 5:
                        ball.change_color_pink()
                    elif punkt == 6:
                        ball.change_color_yellow()
                    elif punkt == 7:
                        ball.change_speed_default()
                        default_ball_speed = 4
                    elif punkt == 8:
                        ball.change_speed_10()
                        default_ball_speed = 10
                    elif punkt == 9:
                        ball.change_speed_12()
                        default_ball_speed = 12
                    elif punkt == 10:
                        ball.change_speed_14()
                        default_ball_speed = 14
                    elif punkt == 11:
                        ball.change_speed_16()
                        default_ball_speed = 16
                    elif punkt == 12:
                        ball.change_speed_18()
                        default_ball_speed = 18
                    elif punkt == 13:
                        ball.change_speed_20()
                        default_ball_speed = 20
                    elif punkt == 14:
                        ball.change_size_default()
                    elif punkt == 15:
                        ball.change_size_20()
                    elif punkt == 16:
                        ball.change_size_30()
                    elif punkt == 17:
                        ball.change_size_40()
                    elif punkt == 18:
                        ball.change_size_50()
                    elif punkt == 19:
                        ball.change_size_60()
                    elif punkt == 20:
                        ball.change_size_70()

            window.blit(font_menu.render('Ball color', 1, (0, 255, 120)), (40, 20))
            window.blit(font_menu.render('Ball speed', 1, (0, 255, 120)), (400, 20))
            window.blit(font_menu.render('Ball size', 1, (0, 255, 120)), (790, 20))
            main_surface.blit(window, (0, 0))
            window.fill((0, 0, 0))
            pygame.display.flip()


punkts_3 = [(50, 130, 'Default', (255, 180, 0), (255, 255, 255), 0),
            (50, 200, 'Blue', (255, 180, 0), (0, 25, 255), 1),
            (50, 270, 'Red', (255, 180, 0), (255, 0, 0), 2),
            (50, 340, 'Green', (255, 180, 0), (0, 255, 0), 3),
            (50, 410, 'Orange', (255, 180, 0), (255, 255, 255), 4),
            (50, 480, 'Purple', (255, 180, 0), (128, 0, 128), 5),
            (50, 550, 'Yellow', (255, 180, 0), (255, 255, 0), 6),
            (400, 130, 'Default', (255, 180, 0), (0, 150, 250), 7),
            (400, 200, '10', (255, 180, 0), (0, 150, 250), 8),
            (400, 270, '12', (255, 180, 0), (0, 150, 250), 9),
            (400, 340, '14', (255, 180, 0), (0, 150, 250), 10),
            (400, 410, '16', (255, 180, 0), (0, 150, 250), 11),
            (400, 480, '18', (255, 180, 0), (0, 150, 250), 12),
            (400, 550, '20', (255, 180, 0), (0, 150, 250), 13),
            (800, 130, 'Default', (255, 180, 0), (0, 150, 250), 14),
            (800, 200, '20px', (255, 180, 0), (0, 150, 250), 15),
            (800, 270, '30px', (255, 180, 0), (0, 150, 250), 16),
            (800, 340, '40px', (255, 180, 0), (0, 150, 250), 17),
            (800, 410, '50px', (255, 180, 0), (0, 150, 250), 18),
            (800, 480, '60px', (255, 180, 0), (0, 150, 250), 19),
            (800, 550, '70px', (255, 180, 0), (0, 150, 250), 20)]

menu_ball_settings = MenuBall(punkts_3)


class MenuColor:
    def __init__(self, punkts_2=[150, 140, 'Punkt', (250, 250, 30), (250, 30, 250), 0]):
        self.punkts_2 = punkts_2

    def render(self, powerh, font, num_pnkt):
        for i in self.punkts_2:
            if num_pnkt == i[5]:
                powerh.blit(font.render(i[2], 1, i[4]), (i[0], i[1] - 30))
            else:
                powerh.blit(font.render(i[2], 1, i[3]), (i[0], i[1] - 30))

    def menu(self):
        global black
        global white
        window = pygame.Surface((1024, 600))
        pygame.key.set_repeat(0, 0)
        pygame.mouse.set_visible(True)
        done = True
        font_menu = pygame.font.SysFont('Arial', 50)
        punkt = 0
        while done:
            mm = pygame.mouse.get_pos()
            for i in self.punkts_2:
                if mm[0] > i[0] and mm[0] < i[0] + 155 and mm[1] > i[1] and mm[1] < i[1] + 50:
                    punkt = i[5]
            self.render(window, font_menu, punkt)
            for e in pygame.event.get():
                if e.type == pygame.QUIT:
                    sys.exit()
                if e.type == pygame.KEYDOWN:
                    if e.key == pygame.K_ESCAPE:
                        done = False
                    if e.key == pygame.K_UP:
                        if punkt == 0:
                            punkt = len(self.punkts_2)
                        if punkt > 0:
                            punkt -= 1
                    if e.key == pygame.K_DOWN:
                        if punkt == 13:
                            punkt = (len(self.punkts_2)) - (len(self.punkts_2) + 1)
                        if punkt < len(self.punkts_2) - 1:
                            punkt += 1
                    if e.key == pygame.K_RETURN:
                        if punkt == 0:
                            change_bg_color_default()
                        elif punkt == 1:
                            change_bg_color_blue()
                        elif punkt == 2:
                            change_bg_color_red()
                        elif punkt == 3:
                            change_bg_color_green()
                        elif punkt == 4:
                            change_bg_color_orange()
                        elif punkt == 5:
                            change_bg_color_pink()
                        elif punkt == 6:
                            change_bg_color_yellow()
                        elif punkt == 7:
                            white = (255, 255, 255)
                        elif punkt == 8:
                            white = blue
                        elif punkt == 9:
                            white = red
                        elif punkt == 10:
                            white = green
                        elif punkt == 11:
                            white = orange
                        elif punkt == 12:
                            white = purple
                        elif punkt == 13:
                            white = yellow

                if e.type == pygame.MOUSEBUTTONDOWN and e.button == 1:
                    if punkt == 0:
                        done = False
                    elif punkt == 1:
                        sys.exit()
                    elif punkt == 2:
                        pass
                    elif punkt == 3:
                        pass
                    elif punkt == 4:
                        change_bg_color_default()
                    elif punkt == 5:
                        change_bg_color_blue()
                    elif punkt == 6:
                        change_bg_color_red()
                    elif punkt == 7:
                        change_bg_color_green()
                    elif punkt == 8:
                        change_bg_color_orange()
                    elif punkt == 9:
                        change_bg_color_pink()
                    elif punkt == 10:
                        change_bg_color_yellow()

            window.blit(font_menu.render('Other subject', 1, (0, 255, 120)), (755, 20))
            window.blit(font_menu.render('Background', 1, (0, 255, 120)), (30, 20))
            main_surface.blit(window, (0, 0))
            window.fill((0, 0, 0))
            pygame.display.flip()


punkts_2 = [(50, 130, 'Default', (255, 180, 0), (255, 255, 255), 0),
            (50, 200, 'Blue', (255, 180, 0), (0, 25, 255), 1),
            (50, 270, 'Red', (255, 180, 0), (255, 0, 0), 2),
            (50, 340, 'Green', (255, 180, 0), (0, 255, 0), 3),
            (50, 410, 'Orange', (255, 180, 0), (255, 255, 255), 4),
            (50, 480, 'Purple', (255, 180, 0), (128, 0, 128), 5),
            (50, 550, 'Yellow', (255, 180, 0), (255, 255, 0), 6),
            (800, 130, 'Default', (255, 180, 0), (255, 255, 255), 7),
            (800, 200, 'Blue', (255, 180, 0), (0, 25, 255), 8),
            (800, 270, 'Red', (255, 180, 0), (255, 0, 0), 9),
            (800, 340, 'Green', (255, 180, 0), (0, 255, 0), 10),
            (800, 410, 'Orange', (255, 180, 0), (255, 255, 255), 11),
            (800, 480, 'Purple', (255, 180, 0), (128, 0, 128), 12),
            (800, 550, 'Yellow', (255, 180, 0), (255, 255, 0), 13)]

menu_color = MenuColor(punkts_2)


class Menu:
    def __init__(self, punkts=[150, 140, 'Punkt', (250, 250, 30), (250, 30, 250), 0]):
        self.punkts = punkts

    def render(self, powerh, font, num_pnkt):
        for i in self.punkts:
            if num_pnkt == i[5]:
                powerh.blit(font.render(i[2], 1, i[4]), (i[0], i[1] - 30))
            else:
                powerh.blit(font.render(i[2], 1, i[3]), (i[0], i[1] - 30))

    def menu(self):
        global black
        global white
        window = pygame.Surface((1024, 600))
        pygame.key.set_repeat(0, 0)
        pygame.mouse.set_visible(True)
        done = True
        font_menu = pygame.font.SysFont('Arial', 50)
        font_mksd = pygame.font.SysFont('Times New Roman', 20)
        punkt = 0
        while done:
            mm = pygame.mouse.get_pos()
            for i in self.punkts:
                if mm[0] > i[0] and mm[0] < i[0] + 155 and mm[1] > i[1] and mm[1] < i[1] + 50:
                    punkt = i[5]
            self.render(window, font_menu, punkt)
            for e in pygame.event.get():
                if e.type == pygame.QUIT:
                    sys.exit()
                if e.type == pygame.KEYDOWN:
                    if e.key == pygame.K_ESCAPE:
                        done = False
                    if e.key == pygame.K_UP:
                        if punkt == 0:
                            punkt = len(self.punkts)
                        if punkt > 0:
                            punkt -= 1
                    if e.key == pygame.K_DOWN:
                        if punkt == 4:
                            punkt = (len(self.punkts)) - (len(self.punkts) + 1)
                        if punkt < len(self.punkts) - 1:
                            punkt += 1
                    if e.key == pygame.K_RETURN:
                        if punkt == 0:
                            done = False
                        elif punkt == 1:
                            menu_color.menu()
                        elif punkt == 2:
                            menu_ball_settings.menu()
                        elif punkt == 3:
                            menu_rackets_settings.menu()
                        elif punkt == 4:
                            sys.exit()

                if e.type == pygame.MOUSEBUTTONDOWN and e.button == 1:
                    if punkt == 0:
                        done = False
                    elif punkt == 1:
                        menu_color.menu()
                    elif punkt == 2:
                        menu_ball_settings.menu()
                    elif punkt == 3:
                        sys.exit()
            window.blit(font_menu.render('Navigation menu', 1, (0, 255, 120)), (355, 0))
            window.blit(font_mksd.render('Created by MKSD', 1, (255, 80, 0)), (870, 570))
            main_surface.blit(window, (0, 0))
            window.fill((0, 0, 0))
            pygame.display.flip()


class Racket(pygame.sprite.Sprite):
    def __init__(self, player_number):

        pygame.sprite.Sprite.__init__(self)
        self.image = pygame.Surface([10, 100])
        self.image.fill(white)
        self.player_number = player_number
        self.rect = self.image.get_rect()
        self.speed = 8

        if self.player_number == 1:
            self.rect.centerx = main_surface.get_rect().left
            self.rect.centerx += 50
        elif self.player_number == 2:
            self.rect.centerx = main_surface.get_rect().right
            self.rect.centerx -= 50
        self.rect.centery = main_surface.get_rect().centery

    def move(self):
        if self.player_number == 1:
            if (UP1 == True) and (self.rect.y > 5):
                self.rect.y -= self.speed
            elif (DOWN1 == True) and (self.rect.bottom < WINDOW_HEIGHT - 5):
                self.rect.y += self.speed
            elif (NO_MOVEMENT1 == True):
                pass

        if self.player_number == 2:
            if (UP2 == True) and (self.rect.y > 5):
                self.rect.y -= self.speed
            elif (DOWN2 == True) and (self.rect.bottom < WINDOW_HEIGHT - 5):
                self.rect.y += self.speed
            elif (NO_MOVEMENT2 == True):
                pass

    def change_size_default(self):
        self.image = pygame.Surface([10, 100])
        self.image.fill(white)

    def change_size_3(self):
        self.image = pygame.Surface([5, 25])
        self.image.fill(white)

    def change_size_5(self):
        self.image = pygame.Surface([10, 50])
        self.image.fill(white)

    def change_size_15(self):
        self.image = pygame.Surface([15, 150])
        self.image.fill(white)

    def change_size_20(self):
        self.image = pygame.Surface([20, 200])
        self.image.fill(white)

    def change_speed_default(self):
        self.speed = 8

    def change_speed_10(self):
        self.speed = 10

    def change_speed_12(self):
        self.speed = 12

    def change_speed_14(self):
        self.speed = 14

    def change_speed_16(self):
        self.speed = 16

    def change_speed_18(self):
        self.speed = 18

    def change_speed_20(self):
        self.speed = 20

    def change_color_default(self):
        self.image.fill(white)

    def change_color_blue(self):
        self.image.fill(blue)

    def change_color_red(self):
        self.image.fill(red)

    def change_color_green(self):
        self.image.fill(green)

    def change_color_orange(self):
        self.image.fill(orange)

    def change_color_pink(self):
        self.image.fill(purple)

    def change_color_yellow(self):
        self.image.fill(yellow)


class Ball(pygame.sprite.Sprite):
    def __init__(self):
        pygame.sprite.Sprite.__init__(self)
        self.image = pygame.Surface((10, 10))
        self.image.fill(white)
        self.rect = self.image.get_rect()
        self.rect.centerx = surface_rect.centerx
        self.rect.centery = surface_rect.centery
        self.direction = randint(0, 3)
        self.speed = 4

    def move(self):
        if self.direction == UPLEFT:
            self.rect.x -= self.speed
            self.rect.y -= self.speed
        elif self.direction == UPRIGHT:
            self.rect.x += self.speed
            self.rect.y -= self.speed
        elif self.direction == DOWNLEFT:
            self.rect.x -= self.speed
            self.rect.y += self.speed
        elif self.direction == DOWNRIGHT:
            self.rect.x += self.speed
            self.rect.y += self.speed

    def change_direction(self):
        if self.rect.y < 0 and self.direction == UPLEFT:
            self.direction = DOWNLEFT
        if self.rect.y < 0 and self.direction == UPRIGHT:
            self.direction = DOWNRIGHT
        if self.rect.y > surface_rect.bottom and self.direction == DOWNLEFT:
            self.direction = UPLEFT
        if self.rect.y > surface_rect.bottom and self.direction == DOWNRIGHT:
            self.direction = UPRIGHT

    def change_size_default(self):
        self.image = pygame.Surface((10, 10))
        self.image.fill(white)

    def change_size_20(self):
        self.image = pygame.Surface((20, 20))
        self.image.fill(white)

    def change_size_30(self):
        self.image = pygame.Surface((30, 30))
        self.image.fill(white)

    def change_size_40(self):
        self.image = pygame.Surface((40, 40))
        self.image.fill(white)

    def change_size_50(self):
        self.image = pygame.Surface((50, 50))
        self.image.fill(white)

    def change_size_60(self):
        self.image = pygame.Surface((60, 60))
        self.image.fill(white)

    def change_size_70(self):
        self.image = pygame.Surface((70, 70))
        self.image.fill(white)

    def change_speed_default(self):
        self.speed = 8

    def change_speed_10(self):
        self.speed = 10

    def change_speed_12(self):
        self.speed = 12

    def change_speed_14(self):
        self.speed = 14

    def change_speed_16(self):
        self.speed = 16

    def change_speed_18(self):
        self.speed = 18

    def change_speed_20(self):
        self.speed = 20

    def change_color_default(self):
        self.image.fill(white)

    def change_color_blue(self):
        self.image.fill(blue)

    def change_color_red(self):
        self.image.fill(red)

    def change_color_green(self):
        self.image.fill(green)

    def change_color_orange(self):
        self.image.fill(orange)

    def change_color_pink(self):
        self.image.fill(purple)

    def change_color_yellow(self):
        self.image.fill(yellow)


basic_font = pygame.font.SysFont("Helvetica", 120)
game_over_font_big = pygame.font.SysFont("Helvetica", 72)
game_over_font_small = pygame.font.SysFont("Helvetica", 50)
font_mksd = pygame.font.SysFont('Times New Roman', 20)

punkts = [(50, 140, 'Play', (255, 192, 0), (0, 150, 250), 0),
          (50, 210, 'Change color', (255, 192, 0), (0, 150, 250), 1),
          (50, 280, 'Ball settings', (255, 192, 0), (0, 150, 250), 2),
          (50, 350, 'Rackets settings', (255, 192, 0), (0, 150, 250), 3),
          (50, 410, 'Quit', (255, 192, 0), (0, 150, 250), 4)]

racket1 = Racket(1)
racket2 = Racket(2)
ball = Ball()

game = Menu(punkts)
game.menu()

all_sprites = pygame.sprite.RenderPlain(racket1, racket2, ball)

player1_score = 0
player2_score = 0


def racket_hit():
    if pygame.sprite.collide_rect(ball, racket2):
        if (ball.direction == UPRIGHT):
            ball.direction = UPLEFT
        elif (ball.direction == DOWNRIGHT):
            ball.direction = DOWNLEFT
        ball.speed += 1
    elif pygame.sprite.collide_rect(ball, racket1):
        if (ball.direction == UPLEFT):
            ball.direction = UPRIGHT
        elif (ball.direction == DOWNLEFT):
            ball.direction = DOWNRIGHT
        ball.speed += 1


counter = 0

main = True
while main:
    clock.tick(60)
    pygame.mouse.set_visible(False)
    if (ball.rect.x > WINDOW_WIDTH):
        ball.rect.centerx = surface_rect.centerx
        ball.rect.centery = surface_rect.centery
        ball.direction = randint(0, 1)
        ball.speed = default_ball_speed
    elif (ball.rect.x < 0):
        ball.rect.centerx = surface_rect.centerx
        ball.rect.centery = surface_rect.centery
        ball.direction = randint(2, 3)
        ball.speed = default_ball_speed

    for event in pygame.event.get():
        if event.type == QUIT:
            pygame.quit()
            sys.exit()

        if event.type == KEYDOWN:
            if event.key == K_ESCAPE:
                game.menu()

            if event.key == ord('w'):
                UP1 = True
                DOWN1 = False
                NO_MOVEMENT1 = False
            elif event.key == ord('s'):
                UP1 = False
                DOWN1 = True
                NO_MOVEMENT1 = False

            elif event.key == K_UP:
                UP2 = True
                DOWN2 = False
                NO_MOVEMENT2 = False
            elif event.key == K_DOWN:
                UP2 = False
                DOWN2 = True
                NO_MOVEMENT2 = False

        elif event.type == KEYUP:
            if event.key == ord('w') or event.key == ord('s'):
                NO_MOVEMENT1 = True
                DOWN1 = False
                UP1 = False
            elif event.key == K_DOWN or event.key == K_UP:
                NO_MOVEMENT2 = True
                DOWN2 = False
                UP2 = False

    score_board = basic_font.render(str(player1_score) + "           " + str(player2_score), True, white, black)
    score_board_rect = score_board.get_rect()
    score_board_rect.centerx = surface_rect.centerx
    score_board_rect.y = 10

    main_surface.fill(black)

    main_surface.blit(score_board, score_board_rect)

    netx = surface_rect.centerx

    net_rect0 = pygame.Rect(netx, 0, 5, 5)
    net_rect1 = pygame.Rect(netx, 60, 5, 5)
    net_rect2 = pygame.Rect(netx, 120, 5, 5)
    net_rect3 = pygame.Rect(netx, 180, 5, 5)
    net_rect4 = pygame.Rect(netx, 240, 5, 5)
    net_rect5 = pygame.Rect(netx, 300, 5, 5)
    net_rect6 = pygame.Rect(netx, 360, 5, 5)
    net_rect7 = pygame.Rect(netx, 420, 5, 5)
    net_rect8 = pygame.Rect(netx, 480, 5, 5)
    net_rect9 = pygame.Rect(netx, 540, 5, 5)
    net_rect10 = pygame.Rect(netx, 595, 5, 5)

    pygame.draw.rect(main_surface, white, (net_rect0.left, net_rect0.top, net_rect0.width, net_rect0.height))
    pygame.draw.rect(main_surface, white, (net_rect1.left, net_rect1.top, net_rect1.width, net_rect1.height))
    pygame.draw.rect(main_surface, white, (net_rect2.left, net_rect2.top, net_rect2.width, net_rect2.height))
    pygame.draw.rect(main_surface, white, (net_rect3.left, net_rect3.top, net_rect3.width, net_rect3.height))
    pygame.draw.rect(main_surface, white, (net_rect4.left, net_rect4.top, net_rect4.width, net_rect4.height))
    pygame.draw.rect(main_surface, white, (net_rect5.left, net_rect5.top, net_rect5.width, net_rect5.height))
    pygame.draw.rect(main_surface, white, (net_rect6.left, net_rect6.top, net_rect6.width, net_rect6.height))
    pygame.draw.rect(main_surface, white, (net_rect7.left, net_rect7.top, net_rect7.width, net_rect7.height))
    pygame.draw.rect(main_surface, white, (net_rect8.left, net_rect8.top, net_rect8.width, net_rect8.height))
    pygame.draw.rect(main_surface, white, (net_rect9.left, net_rect9.top, net_rect9.width, net_rect9.height))
    pygame.draw.rect(main_surface, white, (net_rect10.left, net_rect10.top, net_rect10.width, net_rect10.height))

    all_sprites.draw(main_surface)
    racket1.move()
    racket2.move()
    ball.move()
    ball.change_direction()

    racket_hit()

    if ball.rect.x > WINDOW_WIDTH:
        player1_score += 1
    elif ball.rect.x < 0:
        player2_score += 1

    pygame.display.update()

    if counter == 0:
        time.sleep(1.5)

    if player1_score == 10:
        player1_win = True
        score_board = True
        main = False
    elif player2_score == 10:
        player2_win = True
        score_board = True
        main = False

    counter += 1

score_board = True
while score_board:

    for event in pygame.event.get():
        if event.type == QUIT:
            pygame.quit()
            sys.exit()

        if event.type == KEYDOWN:
            if event.key == K_ESCAPE:
                game.menu()
                pygame.quit()
            elif event.key == K_SPACE:
                pygame.quit()
                sys.exit()

    main_surface.fill(black)

    if player1_win is True:
        game_over = game_over_font_big.render("GAME OVER", True, white, black)
        game_over1 = game_over_font_small.render("Player 1 Wins", True, white, black)
        quit = game_over_font_small.render("Click 'Space' to quit the game", True, white, black)
        created = font_mksd.render('Created by MKSD', 1, (255, 80, 0)), (870, 570)
    elif player2_win is True:
        game_over = game_over_font_big.render("GAME OVER", True, white, black)
        game_over1 = game_over_font_small.render("Player 2 Wins", True, white, black)
        quit = game_over_font_small.render("Click 'Space' to quit the game", True, white, black)
        created = font_mksd.render("Created by MKSD", True, (255, 80, 0), black)

    game_over_rect = game_over.get_rect()
    game_over_rect.centerx = surface_rect.centerx
    game_over_rect.centery = surface_rect.centery - 50
    game_over1_rect = game_over1.get_rect()
    game_over1_rect.centerx = game_over_rect.centerx
    game_over1_rect.centery = game_over_rect.centery + 75

    main_surface.blit(game_over, game_over_rect)
    main_surface.blit(game_over1, game_over1_rect)
    main_surface.blit(quit, (250, 450))
    main_surface.blit(created, (870, 570))

    pygame.display.update()

- 👋 Hi, I’m @Rotem844
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Rotem844/Rotem844 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->import pygame
import sys

pygame.init()

# משתנים
WIDTH, HEIGHT = 600, 400
FPS = 30
clock = pygame.time.Clock()
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Animated Game")

# צבעים
WHITE = (255, 255, 255)

# מסך הבית
def home_screen():
    screen.fill(WHITE)
    font = pygame.font.Font(None, 36)
    text = font.render("Press SPACE to play!", True, (0, 0, 0))
    screen.blit(text, (WIDTH // 4, HEIGHT // 2))
    pygame.display.flip()

# מסך המשחק
def game_screen():
    running = True
    x = 50
    y = HEIGHT // 2
    speed = 5

    while running:
        clock.tick(FPS)
        screen.fill(WHITE)

        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                running = False

        keys = pygame.key.get_pressed()
        if keys[pygame.K_SPACE]:
            x += speed

        pygame.draw.rect(screen, (0, 128, 255), (x, y, 50, 50))
        pygame.display.flip()

    pygame.quit()
    sys.exit()

# משחק עם אנימציה
def main():
    running = True
    home_screen()

    while running:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                running = False
            elif event.type == pygame.KEYDOWN:
                if event.key == pygame.K_SPACE:
                    game_screen()

if __name__ == "__main__":
    main()



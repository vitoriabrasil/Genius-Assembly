# Genius-Assembly

Sobre o Processador e Montador

## Apenas para github space:

Xvfb :1 -screen 0 1280x800x24 +extension GLX +render -noreset > /tmp/xvfb.log 2>&1 &
x11vnc -display :1 -forever -shared -localhost -nopw -rfbport 5900 > /tmp/x11vnc.log 2>&1 &
websockify --web=/usr/share/novnc 6080 localhost:5900 > /tmp/novnc.log 2>&1 &

### FECHAR VNC :

pkill -f websockify
pkill -f x11vnc
pkill -f Xvfb
Apenas para github space:

### abrir de novo:

Xvfb :1 -screen 0 1280x800x24 +extension GLX +render -noreset > /tmp/xvfb.log 2>&1 &
x11vnc -display :1 -forever -shared -localhost -nopw -rfbport 5900 > /tmp/x11vnc.log 2>&1 &
websockify --web=/usr/share/novnc 6080 localhost:5900 > /tmp/novnc.log 2>&1 &

DISPLAY=:1 LIBGL_ALWAYS_SOFTWARE=1 [comando]
exemplo:
DISPLAY=:1 LIBGL_ALWAYS_SOFTWARE=1 ./saida genius.mif charmap.mif

https://vigilant-broccoli-g499g5vpg7qjh97jx-6080.app.github.dev/vnc.html
./s genius.asm genius.mif

https://vigilant-broccoli-g499g5vpg7qjh97jx-6080.app.github.dev/

## geral:

cd /workspaces/processador_e_montador/montador-main/Simulator_Source

g++ -std=c++11 main.cpp Controller.cpp Model.cpp Sound.cpp View.cpp $(pkg-config --cflags --libs gtk+-2.0 sdl2) -lGL -lm -o saida


# Calculadora de perdidas

Herramienta de Valeria e Ivan para hacer en vivo, durante una llamada, la cuenta de lo que una
clinica pierde cuando los mensajes se quedan sin contestar. Se publica con GitHub Pages, asi que
este repositorio es publico: **no se le agrega nada que no pueda estar a la vista.**

Hoy no lleva costos ni margenes. Solo la formula, el supuesto conservador y una cita con fuente.

La documentacion completa (de donde sale la formula, que se puede afirmar y que no, y como se
usa en la llamada) vive en el repo de EVA, en `templates/calculadora-fuga/README.md`.

La formula sale del bloque 3 del guion de llamada, `hb-wiki/wiki/interno/ventas/llamada-15-min.md`.
**La wiki manda; este archivo la implementa.**

## Como se actualiza

**`index.html` de este repo es generado. No se edita aqui.** La fuente esta en EVA, en
`templates/calculadora-fuga/index.html`, y se publica asi:

```
cd ../eva/templates/calculadora-fuga
python3 construir.py          # escribe index.html en este repo
cd ../../../calculadora
git commit -am "..." && git push
```

GitHub Pages republica solo en un par de minutos, en la misma URL.

La misma fuente alimenta un Artifact privado en Claude, que es la version que se usa sin salir
del chat. Las dos salen de correr `construir.py`, asi que no se desincronizan.

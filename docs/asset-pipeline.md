# Pipeline de recursos HD-2D — Liora

## Objetivo
O Liora recebe recursos prontos produzidos no Berofel HD-2D Studio. O Studio permanece um projeto independente; este repositório contém apenas contratos, manifests e futuramente os assets aprovados para o jogo.

## Formato de entrega
Cada pacote de personagem deve incluir:
- `character.json`: metadados, pivôs, ordem de camadas, perfil de rig e direções.
- `spritesheet.png`: quadros agrupados por animação/direção.
- `preview.png`: imagem de conferência.
- `parts/`: peças transparentes independentes quando houver rig modular.
- `effects/`: efeitos visuais reutilizáveis, sem dependência do editor.

## Convenções
- PNG com transparência; pixel art sem interpolação suavizada.
- Origem/pivô e dimensões declarados no JSON.
- FPS, duração dos frames e loop explícitos.
- Direções canônicas: south, south_east, east, north_east, north, north_west, west, south_west.
- Não presumir que uma direção ausente pode ser espelhada: registrar a política no manifesto.
- Não incluir chaves, tokens ou credenciais em assets ou no cliente do jogo.

## Organização futura
```
game_assets/
  characters/<character-id>/
    character.json
    preview.png
    spritesheet.png
    parts/
  effects/<effect-id>/
    effect.json
    spritesheet.png
  manifest.json
```

## Validação antes de integrar
1. Conferir transparência e dimensões.
2. Conferir alinhamento dos pivôs entre frames.
3. Reproduzir cada animação sem saltos.
4. Verificar as oito direções; marcar explicitamente direções ainda não produzidas.
5. Conferir licença e origem de cada recurso externo.
6. Só então aprovar o pacote para uso no jogo.

## Estado atual
Este commit adiciona o contrato e a estrutura inicial. Ainda não adiciona personagens finais, animações finais, efeitos PixelFX nem uma integração de runtime Godot. O editor Berofel HD-2D Studio continua separado.

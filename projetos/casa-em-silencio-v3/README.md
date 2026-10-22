# A casa em silêncio — versão 3

Filme de 50 segundos, 1920 × 1080, 30 fps, sem áudio. Conteúdo essencial no centro para recorte vertical. Revisão com cena 3D animada, câmera, materiais metálicos, plataformas articuladas, figuras estilizadas e sombras, inspirada no vídeo Gemini enviado pelo cliente. São modelos próprios; nenhum trecho da referência foi incorporado.

## Editar

1. Extraia o ZIP inteiro, mantendo as pastas.
2. Instale Inter a partir de `assets/fonts` antes de abrir o projeto.
3. Abra `filme-3d-effectcraft.ecproj` no EffectCraft 0.14.0 ou posterior. Os 37 textos e seus movimentos ficam na composição `CORE_TEXTOS_EDITAVEIS_608x1080`. O master horizontal usa essa composição e o vídeo 3D de fundo. A composição vertical recorta o master.
4. Abra `src/cena-3d.blend` no Blender 4.3 ou posterior para editar os modelos, materiais, câmera e animações. A linha do tempo usa 30 fps, quadros 1–1500.

Para levar alterações manuais do Blender ao render web, salve o `.blend` e execute:

```sh
blender -b src/cena-3d.blend --python src/exportar-blend.py
node src/renderizar.cjs
bash src/exportar-entregas.sh
```

`modelar-cena.py` reconstrói tudo a partir do código: não o execute sobre uma edição manual sem guardar uma cópia. `exportar-blend.py` exporta o arquivo já editado sem reconstruir seus objetos. Preserve a câmera ortográfica ativa e os nomes dos grupos principais, usados para controlar a visibilidade no render web.

O cenário 3D é um vídeo de fundo dentro do EffectCraft. A geometria permanece editável no Blender. Alterações em objetos ou câmera exigem renderizar novamente o cenário; os textos continuam independentes e editáveis no EffectCraft. O render web usa iluminação própria, por isso o render direto do Blender terá diferenças de luz e materiais.

## Reproduzir o pipeline gratuito

Requisitos: Blender 4.3, Node.js, Chromium, FFmpeg, Python 3 e EffectCraft CLI 0.14.0. No ambiente deste projeto o executável CLI está em `/workspace/tools/bin/effectcraft-cli` e Chromium em `/usr/bin/chromium`; ajuste esses caminhos nos scripts para outro sistema.

```sh
npm ci --ignore-scripts --no-audit --no-fund
blender -b -t 4 --python src/modelar-cena.py
node src/renderizar.cjs --proof
node src/renderizar.cjs
python3 src/compor-effectcraft.py
```

A cena Blender é exportada para GLB e renderizada por Three.js com materiais PBR e sombras a cada quadro. O arquivo `assets/textos-base.ecproj` preserva a tipografia animada para regeneração. O script de composição importa o vídeo 3D no EffectCraft. A versão entregue já contém todos os arquivos necessários para editar sem executar esses scripts.

Inter é uma aproximação editorial; a família exata da referência não foi identificada. Inter usa OFL; Three.js usa MIT, licenças incluídas. Modelos 3D e textura da fatura são do projeto. Não foram contratados serviços pagos. Sem voz, trilha ou efeitos: a sincronização fina pode ser ajustada após receber a locução.

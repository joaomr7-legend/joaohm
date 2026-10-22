# Evidências e limites da versão 3

- Cenário 3D: 1920×1080, 50,000 s, 30 fps, 1.500 quadros, H.264, sem áudio. Decodificação integral por FFmpeg concluída sem erros.
- Modelos, câmera e animações editáveis em src/cena-3d.blend. Exportação desse arquivo já salvo exercitada pelo script exportar-blend.py; GLB resultante válido com 252 animações e câmera ortográfica.
- O render usa uma cena 3D por quadro, materiais PBR e sombras VSM no Three.js. Não é ray tracing. O Blender armazena os modelos e a câmera; o render web usa sua própria iluminação. Dentro do EffectCraft, o cenário é uma camada de vídeo; as malhas não são editáveis nesse programa.
- EffectCraft 0.14.0: 37 camadas nativas de texto no CORE, master horizontal e composição vertical ligada ao master. Fonte Inter aproximada, sem identificação exata da família da referência.
- Nenhuma mídia ausente na inspeção do projeto. Projeto e assets copiados para outra pasta; nenhuma mídia ausente e quadro vertical em 49 s renderizado com sucesso. Caminhos de mídia relativos.
- Revisão visual por quadros: abertura, destaque tipográfico e plataformas, segunda, quarta, domingo após apagar a chama e conclusão. Amostras horizontais e verticais inspecionadas. Isso não equivale a reprodução visual integral em velocidade real.
- Conteúdo principal centralizado para recorte vertical; piso e sombras podem ultrapassar a faixa central. Figuras são miniaturas estilizadas, não pessoas fotorrealistas.
- Interface gráfica do EffectCraft não foi testada em desktop; CLI, projeto, mídia, fontes e quadros foram exercitados.
- Referências examinadas por amostragem temporal, incluindo transições. Nenhum quadro ou áudio de referência foi distribuído.
- Sem voz, música ou efeitos. A sincronização fina aguarda a locução do cliente.

## Exportação final verificada

- Render nativo do EffectCraft concluído com código 0: 1.500 quadros em 249,15 segundos. Decodificação integral do arquivo nativo por FFmpeg concluída sem erros.
- Horizontal: 1920×1080, 50,000 s, 30 fps, 1.500 quadros, H.264 Main, yuv420p, sem áudio. Decodificação integral sem erros.
- Vertical: 1080×1920, mesmos parâmetros de duração, quadros e codec. Decodificação integral sem erros. Recorte central de 608×1080 ampliado para 1080×1920; não se trata de render 3D independente nessa resolução.
- MP4 finais usam faststart. Metadados em entrega/verificacao-video.json; hashes em entrega/SHA256SUMS.txt.
- Quadros também extraídos dos MP4 finais em 2,5; 23,5; 28; 37; 43; 44,5 e 49 s. Amostras e recorte vertical revisados, sem reprodução integral em velocidade real.

# ARXIA · Nova identidade para a plataforma
**Para: David · 04/11/2026**

Trocar na plataforma: paleta de cores e logo. Nada de layout, nada de componente novo.

---

## 1. Paleta

Três cores. **Branco é a cor principal**, verde entra só no detalhe, cinza no apoio.

| Token | Hex | Função |
|---|---|---|
| `--bg` | `#FFFFFF` | fundo de tudo |
| `--bg-2` | `#F3F6F7` | superfície secundária, cabeçalho de tabela, linha alternada |
| `--fg` | `#15282D` | texto principal |
| `--muted` | `#5E7075` | texto secundário, legenda |
| `--faint` | `#7E8E93` | texto de apoio, placeholder |
| `--line` | `#E3E8EA` | borda e divisor |
| `--line-2` | `#C9D3D6` | borda de campo e de botão secundário |
| `--verde` | `#126A79` | **cor de marca**, só em detalhe |
| `--verde-escuro` | `#0F5B68` | hover do verde |
| `--verde-claro` | `#17808F` | estado ativo |
| `--verde-suave` | `#EAF3F5` | fundo de selo, destaque leve |
| `--sobre-verde` | `#FFFFFF` | texto em cima do verde |

### Onde o verde pode aparecer
Botão principal, rótulo de seção, filete, ícone, símbolo do logo, barra do topo, estado ativo no menu lateral.

### Onde o verde NÃO pode aparecer
Fundo de tela inteira, fundo de cartão, fundo de tabela, texto corrido.

### Contraste conferido
- `#15282D` sobre branco: **15,3** ✓
- `#5E7075` sobre branco: **5,2** ✓
- `#126A79` sobre branco: **6,2** ✓
- Branco sobre `#126A79`: **6,2** ✓
- `#7E8E93` sobre branco: **3,4** → só para texto acima de 18px ou decorativo

---

## 2. Botões

| Tipo | Fundo | Texto | Borda | Hover |
|---|---|---|---|---|
| Principal | `#126A79` | `#FFFFFF` | nenhuma | fundo `#0F5B68` |
| Secundário | transparente | `#15282D` | 1px `#C9D3D6` | borda `#15282D` |
| Em cima do verde | `#FFFFFF` | `#126A79` | nenhuma | fundo `#EAF3F5` |
| Destrutivo | transparente | `#15282D` | 1px `#C9D3D6` | borda `#15282D` |

**Sem vermelho em lugar nenhum.** Ação destrutiva se diferencia por confirmação, não por cor.

Forma: **raio de 2px**, não pílula. Altura 44px. Fonte 11,5px, peso 600, caixa alta, entreletra `.14em`, padding 17px 30px.

Foco de teclado: contorno de 2px em `#126A79`, deslocado 3px. Obrigatório, não remover.

---

## 3. Estados e avisos

| Estado | Cor | Uso |
|---|---|---|
| Completo / liberado | `#126A79` | selo CAMPOS COMPLETOS, trava liberada |
| Pendente / bloqueado | `#5E7075` sobre `#F3F6F7` | selo INCOMPLETO, botão travado |
| Informação | `#126A79` sobre `#EAF3F5` | caixa da blindagem técnica |

O documento incompleto **não** usa vermelho. Usa cinza mais o texto do motivo.

---

## 4. Logo

Arquivos na pasta `logo/`, todos PNG com fundo transparente.

| Arquivo | Usar em |
|---|---|
| `arxia-lockup-verde.png` | fundo branco ou claro |
| `arxia-lockup-branco.png` | fundo verde ou escuro |
| `arxia-simbolo-verde.png` | favicon, espaço quadrado em fundo claro |
| `arxia-simbolo-branco.png` | espaço quadrado em fundo escuro |

**Regras:**
- Altura mínima do lockup: **32px**. Abaixo disso o descritor não lê, usar só o símbolo.
- Área livre em volta: metade da altura do símbolo, em todos os lados.
- Não distorcer, não girar, não aplicar sombra, não colocar sobre foto sem contraste.
- Favicon: gerar 16, 32 e 180px a partir de `arxia-simbolo-verde.png`.

Em `originais-canva/` estão os seis arquivos como saíram do Canva, em 6250px, caso precise reexportar.

---

## 5. Tipografia

Montserrat, pesos 300, 400, 500, 600 e 700.

- Títulos: peso 300, entreletra `-0.03em`
- Palavra de ênfase dentro do título: peso 600
- Corpo: 400
- Rótulo e botão: 600, caixa alta, entreletra `.14em`
- Número: `font-variant-numeric: tabular-nums`

---

## 6. CSS pronto

```css
:root{
  --bg:#FFFFFF; --bg-2:#F3F6F7;
  --fg:#15282D; --muted:#5E7075; --faint:#7E8E93;
  --line:#E3E8EA; --line-2:#C9D3D6;
  --verde:#126A79; --verde-escuro:#0F5B68; --verde-claro:#17808F;
  --verde-suave:#EAF3F5; --sobre-verde:#FFFFFF;
  --raio:2px;
}
.btn{border-radius:var(--raio);font-size:11.5px;font-weight:600;
     letter-spacing:.14em;text-transform:uppercase;padding:17px 30px;border:1px solid transparent}
.btn-principal{background:var(--verde);color:var(--sobre-verde)}
.btn-principal:hover{background:var(--verde-escuro)}
.btn-secundario{background:transparent;color:var(--fg);border-color:var(--line-2)}
.btn-secundario:hover{border-color:var(--fg)}
:focus-visible{outline:2px solid var(--verde);outline-offset:3px}
```

---

## 7. Pendências que não são suas

Dois itens da marca ainda não estão fechados e podem mudar depois:

1. O descritor do logo está escrito "Plataforma clínica Inteligente", com maiúsculas inconsistentes. Vai ser corrigido para caixa alta.
2. Não existe versão em SVG ainda, só PNG em alta.

Nenhum dos dois impede a troca da paleta. O logo você pode trocar agora e substituir o arquivo depois, se o nome dele for mantido.

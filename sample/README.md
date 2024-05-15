# Build Sample files

## generate PDF Documents

Beispiel DOAG

```bash
echo "generate PDF sample file"
docker run --rm -v "$PWD":/workdir:z oehrlis/pandoc  \
--metadata-file sample/metadata.yml --filter pandoc-latex-environment \
--resource-path=sample --pdf-engine=xelatex \
--listings -o sample/sample.pdf sample/sample.md
```

## generate Word Documents

```bash
echo "generate DOCX sample file"
docker run --rm -v "$PWD":/workdir:z oehrlis/pandoc  \
--metadata-file sample/metadata.yml --resource-path=sample \
--listings -o sample/sample.docx sample/sample.md
```

## generate PPTX

```bash
echo "generate PPTX sample file"
docker run --rm -v "$PWD":/workdir:z oehrlis/pandoc  \
--metadata-file sample/metadata.yml --resource-path=sample \
--listings -o sample/sample.pptx sample/sample.md
```

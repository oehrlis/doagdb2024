# generate PDF

echo "generate PDF sample file"
docker run --rm -v "$PWD":/workdir:z ${DOCKER_USER}/${IMAGE}:$RELEASE  \
--metadata-file sample/metadata.yml --filter pandoc-latex-environment \
--resource-path=sample --pdf-engine=xelatex \
--listings -o sample/sample.pdf sample/sample.md

# generate DOCX

echo "generate DOCX sample file"
docker run --rm -v "$PWD":/workdir:z ${DOCKER_USER}/${IMAGE}:$RELEASE  \
--metadata-file sample/metadata.yml --resource-path=sample \
--listings -o sample/sample.docx sample/sample.md

# generate PPTX

echo "generate PPTX sample file"
docker run --rm -v "$PWD":/workdir:z ${DOCKER_USER}/${IMAGE}:$RELEASE  \
--metadata-file sample/metadata.yml --resource-path=sample \
--listings -o sample/sample.pptx sample/sample.md

# change back to working directory

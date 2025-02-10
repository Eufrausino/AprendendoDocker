#Imagem na qual o arquivo irá se basear (estende)
FROM nginx:1.27.0

#Deleta arquivo de erro 500 criado pelo Docker
RUN rm -rf /usr/share/nginx/html

#O destino da cópia fica dentro do sistema de arquivos da imagem
COPY static /usr/share/nginx/html

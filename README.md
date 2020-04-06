docker-compose settings for Ruby on Rails

�E���̃��|�W�g����clone����

�Erails new��Rails�C���X�g�[��
`docker-compose run web rails new . --force --no-deps --database=postgresql`

�Edocker�r���h
`docker-compose build`

�EDB�R�l�N�V�����ݒ�

```
default: &default
  adapter: postgresql
  encoding: unicode
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
+  host: db
+  username: postgres
+  password: password
```

�EDB�쐬
`docker-compose run web rake db:create`

�E�R���e�i�N��
`docker-compose up -d`

�Ehttp://localhost:3000 �ŃA�N�Z�X������z�[����ʂ��\�������



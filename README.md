# devops-grafana-loki

## Para rodar os containers em docker

    - docker-compose up -d

## Primeiro Acesso ao Grafana

    user: Admin
    Password: Admin

## Criando consultas ao grafana loki

    - {job="gerador-log"} |~ "DEBUG|INFO"
    - {job="gerador-log"} |= "DEBUG"
    - {job="varlogs"} |= "DEBUG"
    - {job="gerador-log"} !~ "DEBUG|INFO"
    - {job="gerador-log"} | logfmt

    - count by (log_level) (rate({job="gerador-log"} | logfmt [1h]))

    # Tipo de Liguagem escrita ao grafana é grafana ql

## Templates Dasboard para consultar log app no Grafana

    - https://grafana.com/grafana/dashboards/13639-logs-app/

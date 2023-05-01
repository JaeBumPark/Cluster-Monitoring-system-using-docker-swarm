# Cluster-Monitoring-system-using-docker-swarm

## Docker swarm으로 Cluster 구축 & Monitoring system 구측

### 사용법

#### docker가 설치되어 있는 환경 & docker swarm join이 되어있는 상태에서 Master host 부분에서 

```yaml
docker service  docker stack deploy -c docker-compose.yml "생성 이름"

```
####  명령어를 통해 Monitoring Opensource deploy

# 프로젝트 상세

## 1. 시연 영상

[![Video Label](http://img.youtube.com/vi/bpdipL9GW84/0.jpg)](https://youtu.be/bpdipL9GW84)


## 2. 서비스 기능

<img width="1004" alt="Untitled (14)" src="https://user-images.githubusercontent.com/100124605/235440637-ae85e691-4d66-41ca-a6d1-36c78b57a961.png">

- Prometheus가 수집한 Server, application들의 정보를 Grafana dashboard로 시각화
- Grafana dashboard내에서 Server의 Disk space, Memory 사용량, Cpu 사용량 등의 정보를 제공
- Server 내 Deploy 되어있는 Container application의 갯수, Application 별 Traffic 등의 정보 제공

## 3. Architecture

![sample (2) (1)](https://user-images.githubusercontent.com/100124605/235440939-d5bdaae5-2512-411d-abc3-090153749f9e.jpg)

- 각 Server node에 배포되어있는 application과 Server node 자체에 대한 Metric 수집을 목표로 CAdvisor, Node-exporter를 docker swarm을 사용해 Container 형태로 deploy
- Server와 Application의 Metrics을 Prometheus가 pull 방식으로 수집하게 하기 위해 docker swarm을 사용해 Docker Master server에 Container 형태로 deploy
- 수집된 Metrics를 Dashboard 형태로 시각화 하도록 Grafana를 docker swarm을 사용해 Docker Master server에 Container 형태로 deploy

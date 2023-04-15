# Cluster-Monitoring-system-using-docker-swarm

## Docker swarm으로 Cluster 구축 & Monitoring system 구측

### 사용법

#### docker가 설치되어 있는 환경 & docker swarm join이 되어있는 상태에서 Master host 부분에서 

```yaml
docker service  docker stack deploy -c docker-compose.yml "생성 이름"

```
####  명령어를 통해 Monitoring Opensource deploy

Promethues에게 Target(Worker node1,2의 Cadvisor, Node-exporter)을 참조하게 하기위해


```yaml
docker service  docker stack deploy -c docker-compose.yml "생성 이름"

```

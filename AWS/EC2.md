## 이론

- AWS에서 제공하는 확장 가능하고 신뢰성 높은 클라우드 기반의 가상 서버(인스턴스) 서비스이다.

### 장점

- EC2를 사용하면 사용자는 물리적 서버를 직접 구매하거나 관리할 필요 없이, 필요한 용량과 성능을 제공하는 가상 머신을 쉽게 생성하고 관리할 수 있다.
- 개발자와 기업은 웹 애플리케이션, 데이터베이스, 분석 작업 등을 빠르고 유연하게 배포하고 운영할 수 있다.

### 특징

- **확장 가능성 (Elasticity)**
    - 사용량에 따라 인스턴스의 수와 성능을 쉽게 조정할 수 있다.
    - 이를 통해 트래픽 증가에 대응하여 인스턴스를 추가하거나, 사용량이 줄어들면 인스턴스를 종료하여 비용을 절감할 수 있다.
- **다양한 인스턴스 유형**
    - EC2 는 다양한 인스턴스 유형을 제공하여, 사용자는 애플리케이션 요구사항에 맞는 CPU, 메모리, 스토리지, 네트워크 성능을 선택할 수 있다.
        - ex) 일반 목적형, 컴퓨팅 최적화형, 메모리 최적화형, GPU 기반 인스턴스 등이 있다.
- **안정성과 가용성**
    - EC2는 여러 가용 영역(AZ)에 걸쳐 인스턴스를 배포할 수 있어, 장애 발생 시 자동으로 복구되며, 고가용성을 보장한다.
    - SLA(Service Level Agreement)를 통해 높은 가용성을 보장한다.
- **보안**
    - EC2는 VPC(Virtual Private Cloud)를 통해 네트워크를 격리하고, 보안 그룹과 네트워크 ACL을 통해 인스턴스에 대한 접근을 제어할 수 있다.
    - IAM(Identity and Access Management)을 통해 사용자와 애플리케이션의 접근 권한을 세밀하게 관리할 수 있다.
- **유연한 가격 모델**
    1. 온디맨드 인스턴스 (On-Demand Instances)
        1. 필요할 때 인스턴스를 생성하고 사용한 만큼만 비용을 지불한다. 장기 계약없이 유연하게 사용할 수 있다.
    2. 예약 인스턴스 (Reserved Instances)
        1. 1년 또는 3년의 계약 기간 동안 인스턴스를 예약하여, 할인된 가격으로 사용할 수 있다.
        2. 일정한 용량이 지속적으로 필요한 경우에 유리하다
    3. 스팟 인스턴스 (Spot Instances)
        1. 미사용 컴퓨팅 자원을 경매 방식으로 저렴하게 사용할 수 있다.
        2. 가격이 유동적이며, 일시적인 작업에 적합하다
    4. 전용 호스트(Dedicated Hosts)
        1. 물리적으로 격리된 서버를 사용할 수 있어, 라이선스 요구사항이나 보안 규정을 준수해야 하는 경우에 적합하다.
- **자동화 및 관리 도구**
    - [CLI(Command Line Interface)](https://www.notion.so/CLI-Command-Line-Interface-28a6950d1bac4df6b45a94fd293a02ed?pvs=21), [Amazon Chime SDK](https://www.notion.so/Amazon-Chime-SDK-ad331a3a698c4c018563cc209dcf463c?pvs=21), [CloudFormation](https://www.notion.so/CloudFormation-5f8718244efb4180ac0fe339de61ee3f?pvs=21) 등 다양한 도구와 통합되어 있어, 인프라 관리를 자동화할 수 있다.
    - 이를 통해 인스턴스 배포, 관리, 모니터링 작업을 효율적으로 진행할 수 있다.
- **스토리지 옵션**
    - [EBS(Elastic Block Store)](https://www.notion.so/EBS-Elastic-Block-Store-42486c1879b34fee8b07531c2a0775c4?pvs=21)
        - 인스턴스에 연결 가능한 블록 스토리지로, 데이터베이스, 파일 시스템 등을 저장하는 데 사용된다.
    - **인스턴스 스토어(Instance Store)**
        - 물리적 서버의 로컬 스토리지
        - 임시 데이터 저장에 적합하다. 인스턴스가 종료되면 데이터가 삭제된다.
    - [S3(Simple Storage Service)](https://www.notion.so/S3-Simple-Storage-Service-439ece538235409e90db20bd4ab2d612?pvs=21)
        - 객체 스토리지로, 백업, 데이터 아카이빙, 정적 콘텐츠 제공에 사용된다.

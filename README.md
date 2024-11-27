# 쿠버네티스를 활용한 3-tier 웹서비스 구축

## 📑목차
- [프로젝트 소개](#-프로젝트-소개) 
- [핵심 기술](#-핵심-기술)  
- [기술 스택](#-기술-스택)  
- [아키텍처](#-아키텍처)  
- [PAGE](#-page)  
- [산출물](#-산출물)

## 🖥️ 프로젝트 소개

현대의 카페 환경은 빠르게 변화하고 있으며, 고객들은 더 나은 서비스 경험을 기대하고 있습니다. 

이에 따라, 고객이 직접 주문하고 결제할 수 있는 자가 서비스 시스템을 도입하여 대기 시간을 줄이고 주문 과정을 간소화하는 웹사이트를 구축하게 되었습니다.

이 시스템은 급변하는 고객 수요와 트래픽에 유연하게 대응할 수 있어야 하며, 안정적이고 효율적인 서비스를 제공하는 것이 핵심입니다. 
이를 위해, 본 프로젝트는 **쿠버네티스(Kubernetes)** 를 활용해 **3-Tier 웹서비스 아키텍처**를 구축하고, **오토스케일링**과 **경량화**를 구현하는 것을 목표로 합니다.

- **프론트엔드**: Nginx를 사용하여 사용자 인터페이스를 처리합니다.
- **백엔드**: Tomcat을 기반으로 한 서비스 로직을 제공합니다.
- **데이터베이스**: MySQL을 사용하며, 데이터의 가용성과 무결성을 보장하기 위해 이중화 설정을 적용합니다.

각 서비스는 트래픽 변화에 따라 자동으로 확장/축소될 수 있도록 설계되어, 높은 가용성과 성능을 유지할 수 있습니다.


## 🚀 핵심 기술
| Technology            | Description          |
|-----------------------|---------------------------------------------------------------------------------------------------|
| **HA Multi Cluster**         | 쿠버네티스 멀티클러스터 구성을 통해 고가용성(HA) 환경을 유지하고, 클러스터 간 트래픽 분산 및 장애 복구를 최적화하여 시스템의 안정성을 보장합니다. |
| **Nginx & Docker**      | Nginx를 설정하고 Alpine Linux 기반의 Docker 이미지를 생성하여 정적 파일을 제공하며, 경량화된 환경에서 로드 밸런싱을 최적화하여 트래픽 부하를 효율적으로 관리합니다. |
| **Tomcat & Docker**      | Alpine Linux 기반의 Tomcat Docker 이미지를 사용하여 동적 애플리케이션 서버 환경을 구축하고, 경량화된 설정으로 서버 성능을 최적화하여 안정성을 강화합니다. |
| **MySQL 이중화**      | MySQL 이중화를 통해 데이터베이스의 고가용성을 유지합니다. |
| **Deployment & Probes**    | Deployment와 Probes 설정을 통해 애플리케이션의 가용성과 안정성을 높이고, 서비스의 지속적인 운영을 보장합니다. |
| **ArgoCD & GitHub 연동** | ArgoCD와 GitHub 연동을 통해 자동화하여 배포 안정성을 확보하고, 효율적인 코드 관리와 배포 프로세스를 지원합니다. |
| **Whatap & 모니터링**            | Whatap을 설치하고 모니터링을 설정하여 시스템의 성능을 실시간으로 관리하고, 문제 발생 시 빠르게 대응할 수 있는 환경을 제공합니다. |




## 🛠 기술 스택

<table>
<tr>
 <td align="center">프로그래밍 언어</td>
 <td>
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=JavaScript&logoColor=ffffff"/> <!--Java Script-->  
  <img src="https://img.shields.io/badge/Java-orange?style=for-the-badge&logo=Java&logoColor=white"/> <!--Java-->  
  <img src="https://img.shields.io/badge/html5-E34F26?style=for-the-badge&logo=html5&logoColor=white"/> <!--Html-->   
  <img src="https://img.shields.io/badge/css-1572B6?style=for-the-badge&logo=css3&logoColor=white"/> <!--Css-->  
  <img src="https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=MySQL&logoColor=white"/> <!--Sql-->  
 </td>
</tr>

<tr>
 <td align="center">프레임워크</td>
 <td>
  <img src="https://img.shields.io/badge/JSP-FF5F00?style=for-the-badge&logo=Java&logoColor=white"/> <!--Jsp-->  
  <img src="https://img.shields.io/badge/Spring-6DB33F?style=for-the-badge&logo=Spring&logoColor=ffffff"/> <!--Spring-->  
 </td>
</tr>

<tr>
 <td align="center">인프라</td>
 <td>
  <img src="https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white"/> <!--AWS-->  
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=Kubernetes&logoColor=white"/> <!--Kubernetes-->  
  <img src="https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=Ubuntu&logoColor=white"/> <!--Ubuntu-->   
  <img src="https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=ffffff"/> <!--Docker-->
  <img src="https://img.shields.io/badge/nginx-009639?style=for-the-badge&logo=nginx&logoColor=white"/> <!--Nginx-->
  <img src="https://img.shields.io/badge/tomcat-F8DC75?style=for-the-badge&logo=apachetomcat&logoColor=black"/> <!--Tomcat--> 
  <img src="https://img.shields.io/badge/linux-FCC624?style=for-the-badge&logo=linux&logoColor=black"/> <!--Linux--> 
  <img src="https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white"/> <!--Mysql-->
 </td>
</tr>

<tr>
 <td align="center">협업툴</td>
 <td>
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=Git&logoColor=white"/> <!--Git-->  
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=GitHub&logoColor=white"/> <!--GitHub-->
  <img src="https://img.shields.io/badge/ArgoCD-3C7C7B?style=for-the-badge&logo=argo&logoColor=white"/> <!--ArgoCD-->
 </td>
</tr>

<tr>
 <td align="center">기타</td>
 <td>
  <img src="https://img.shields.io/badge/WhaTap-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhaTap"/> <!--WhaTap--> 
  <img src="https://img.shields.io/badge/Notion-000000?style=for-the-badge&logo=Notion&logoColor=white"/> <!--Notion-->  
  <img src="https://img.shields.io/badge/JSON-000000?style=for-the-badge&logo=json&logoColor=white"/> <!--Json-->  
 </td>
</tr>
</table>



## 🧱 아키텍처
![아키텍처2](https://github.com/user-attachments/assets/51b21d45-36d7-4d28-a90c-713449831930)

![아키텍처](https://github.com/user-attachments/assets/2122fb1f-e767-4385-91d3-a7d9a15db1fb)

## 🌐 PAGE
* 메인
![main](https://github.com/user-attachments/assets/96df65a5-89f8-467d-b6bf-68e5805cc91a)

* 회원가입
![signup](https://github.com/user-attachments/assets/3b25203f-82a3-4933-89d1-0ae9d5f3ac23)

* 주문
![3 주문1](https://github.com/user-attachments/assets/9c4a7c46-41e6-4cb0-acd4-373d6564938c)
![3 주문2](https://github.com/user-attachments/assets/d6695958-955d-4fe2-8cfb-202460f32e42)


## 📦 산출물
JSP는 용량문제로 코드만 첨부합니다.

PPT는 용량문제로 분할 첨부합니다.

* Dockerfile
* yaml
* JSP
* WBS
* 관리대장
* 기술보고서
* 시나리오
* PPT

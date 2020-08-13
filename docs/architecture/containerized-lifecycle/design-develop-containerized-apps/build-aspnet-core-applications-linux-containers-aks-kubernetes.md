---
title: AKS/Kubernetes 클러스터에 Linux 컨테이너로 배포된 ASP.NET Core 애플리케이션 빌드
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 애플리케이션 수명 주기
ms.date: 08/06/2020
ms.openlocfilehash: 4b04e5d56c73918c665ad6e2825205870aac9606
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916455"
---
# <a name="build-aspnet-core-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a>AKS/Kubernetes 오케스트레이터에 Linux 컨테이너로 배포된 ASP.NET Core 애플리케이션 빌드

AKS(Azure Kubernetes Service)는 컨테이너 배포 및 관리를 간소화하는 Azure의 관리형 Kubernetes 오케스트레이션 서비스입니다.

AKS의 주요 기능은 다음과 같습니다.

- Azure에서 호스팅하는 제어 평면
- 자동화된 업그레이드
- 자동 복구
- 사용자 구성 가능 크기 조정
- 개발자와 클러스터 운영자 모두에게 더 간단한 사용자 환경

다음 예제에서는 Visual Studio 2019를 사용하여 개발이 수행되는 동안 Linux에서 실행하고 Azure의 AKS 클러스터에 배포되는 ASP.NET Core 3.1 애플리케이션을 만들어 봅니다.

## <a name="creating-the-aspnet-core-project-using-visual-studio-2019"></a>Visual Studio 2019를 사용하여 ASP.NET Core 프로젝트 만들기

ASP.NET Core는 Microsoft 및 GitHub의 .NET 커뮤니티에서 유지 관리하는 범용 개발 플랫폼입니다. Windows, macOS 및 Linux 플랫폼 간 교차 사용을 지원하며 디바이스, 클라우드 및 포함/IoT 시나리오에서 사용할 수 있습니다.

이 예제에서는 Visual Studio 템플릿을 기준으로 하는 몇 가지 간단한 프로젝트를 사용하므로 샘플을 만들기 위한 추가 지식은 필요하지 않습니다. 표준 템플릿을 사용하여 프로젝트를 만들기만 하면 됩니다. 표준 템플릿에는 ASP.NET Core 3.1 기술을 사용하여 REST API 및 Razor 페이지가 있는 웹앱을 포함하는 소규모 프로젝트를 실행하기 위한 모든 요소가 포함되어 있습니다.

![Visual Studio에서 ASP.NET Core 웹 애플리케이션을 선택하는 새 프로젝트 창을 추가합니다.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-aspnet-core-application.png)

**그림 4-35**. Visual Studio 2019에서 ASP.NET Core 웹 애플리케이션 만들기.

Visual Studio에서 샘플 프로젝트를 만들려면 **파일** > **새로 만들기** > **프로젝트**를 선택하고 **웹** 프로젝트 형식을 선택한 후 **ASP.NET Core 웹 애플리케이션** 템플릿을 선택합니다. 필요한 경우 템플릿을 검색할 수도 있습니다.

다음 이미지에 표시된 것처럼 애플리케이션 이름 및 위치를 입력합니다.

![프로젝트 이름 및 위치를 입력합니다.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/enter-project-name-and-location.png)

**그림 4-36**. Visual Studio 2019에서 프로젝트 이름 및 위치를 입력합니다.

ASP.NET Core 3.1을 프레임워크로 선택했는지 확인합니다. .NET Core 3.1은 Visual Studio 2019의 최신 릴리스에 포함되어 있으며 Visual Studio를 설치하면 자동으로 설치되고 구성됩니다.

![API 옵션이 선택된 상태에서 ASP.NET Core 웹 애플리케이션 유형을 선택하기 위한 Visual Studio 대화 상자](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-web-api-application.png)

**그림 4-37**. ASP.NET CORE 3.1 및 Web API 프로젝트 형식 선택

지금은 Docker 지원이 사용하도록 설정되어 있지 않으므로 프로젝트를 만든 후에 이 작업을 수행할 수 있습니다.

이전 버전의 .NET Core가 있는 경우 <https://dotnet.microsoft.com/download>에서 3.1 버전을 다운로드하여 설치할 수 있습니다.

언제든지 프로젝트를 “Docker화”할 수 있는지 확인하기 위해 지금 Docker 지원을 추가합니다. 솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **추가** > **Docker 지원**을 선택합니다.

![기존 프로젝트에 Docker 지원을 추가하는 바로 가기 메뉴 옵션: (프로젝트에서) 마우스 오른쪽 단추를 클릭하고 추가 > Docker 지원을 클릭합니다.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-docker-support-to-project.png)

**그림 4-38**. 기존 프로젝트에 Docker 지원 추가

Docker 지원 추가를 완료하려면 Windows 또는 Linux를 선택할 수 있습니다. 이 경우 **Linux**를 선택합니다.

![Dockerfile에 대한 대상 OS를 선택하는 옵션 대화 상자](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-linux-docker-support.png)

**그림 4-39**. Linux 컨테이너 선택

이 간단한 단계를 수행하면 Linux 컨테이너에서 실행하는 ASP.NET Core 3.1 애플리케이션이 구현됩니다.

여기에서는 자세히 설명하지 않지만 이와 비슷한 방식으로 간단한 **WebApp** 프로젝트를 추가하여(그림 4-40) 웹 API 엔드포인트를 사용할 수도 있습니다.

그 이후에는 다음 이미지 4-40에 표시되는 것처럼 **WebApi** 프로젝트에 대한 오케스트레이터 지원을 추가합니다.

![WebApi 프로젝트에 오케스트레이터 지원 추가](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-orchestrator-support.png)

**그림 4-40**. *WebApi* 프로젝트에 오케스트레이터 지원 추가

로컬 개발에 적절한 `Docker Compose` 옵션을 선택하는 경우 Visual Studio는 이미지 4-41에 표시된 대로 docker-compose 파일을 사용하여 docker-compose 프로젝트를 추가합니다.

![솔루션에 추가된 docker-compose](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-compose-project-in-visual-studio.png)

**그림 4-41**. *WebApi* 프로젝트에 오케스트레이터 지원 추가

추가된 초기 파일은 다음과 유사합니다.

`docker-compose.yml`

```yml
version: "3.4"

services:
  webapi:
    image: ${DOCKER_REGISTRY-}webapi
    build:
      context: .
      dockerfile: WebApi/Dockerfile

  webapp:
    image: ${DOCKER_REGISTRY-}webapp
    build:
      context: .
      dockerfile: WebApp/Dockerfile
```

`docker-compose.override.yml`

```yml
version: "3.4"

services:
  webapi:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=https://+:443;http://+:80
    ports:
      - "80"
      - "443"
    volumes:
      - ${APPDATA}/Microsoft/UserSecrets:/root/.microsoft/usersecrets:ro
      - ${APPDATA}/ASP.NET/Https:/root/.aspnet/https:ro
  webapp:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=https://+:443;http://+:80
    ports:
      - "80"
      - "443"
    volumes:
      - ${APPDATA}/Microsoft/UserSecrets:/root/.microsoft/usersecrets:ro
      - ${APPDATA}/ASP.NET/Https:/root/.aspnet/https:ro
```

Docker Compose를 사용하여 앱을 실행하려면 `docker-compose.override.yml`을 약간만 조정하면 됩니다.

```yml
services:
  webapi:
    #...
    ports:
      - "51080:80"
      - "51443:443"
    #...
  webapp:
    environment:
      #...
      - WebApiBaseAddress=http://webapi
    ports:
      - "50080:80"
      - "50443:443"
    #...
```

이제 이미지 4-42에 나와 있는 것처럼 **F5** 키를 누르거나, **Play** 단추 또는 **Ctrl+F5** 키를 사용하고 docker-compose 프로젝트를 선택하여 애플리케이션을 실행할 수 있습니다.

![Visual Studio를 사용하여 docker-compose 프로젝트 실행](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/running-docker-compose-with-visual-studio.png)

**그림 4-42**. *WebApi* 프로젝트에 오케스트레이터 지원 추가

설명된 대로 docker-compose 애플리케이션을 실행하는 경우 다음과 같은 결과를 얻게 됩니다.

1. docker-compose 파일별로 빌드된 이미지 및 생성된 컨테이너.
2. 브라우저는 `docker-compose` 프로젝트의 “속성” 대화 상자에 구성된 주소에서 열립니다.
3. **컨테이너** 창이 열립니다(Visual Studio 2019 버전 16.4 이상).
4. 다음 이미지에 표시된 것처럼 솔루션의 모든 프로젝트에 대한 디버거 지원.

열리는 브라우저:

![웹앱이 실행되는 브라우저 보기](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/browser-opened.png)

**그림 4-43**. 애플리케이션이 여러 컨테이너에서 실행되는 브라우저 창.

컨테이너 창:

![Visual Studio “컨테이너” 창](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/visual-studio-containers-window.png)

**그림 4-44**. Visual Studio “컨테이너” 창

**컨테이너** 창에서는 실행 중인 컨테이너를 보고, 사용할 수 있는 이미지를 찾아보고, 환경 변수, 로그 및 포트 매핑을 보고, 파일 시스템을 검사하고, 디버거를 연결하거나, 컨테이너 환경 내에서 터미널 창을 열 수 있습니다.

보다시피 Visual Studio 2019와 Docker는 개발자의 생산성을 최대한 높이는 방법으로 통합되었습니다.

물론 `docker images` 명령을 사용하여 이미지를 나열할 수도 있습니다. Visual Studio 2019를 통해 프로젝트를 자동 배포하여 만든 `webapi` 및 `webapp` 이미지에 `dev` 태그가 지정된 것을 볼 수 있습니다.

```console
docker images
```

![Docker 이미지 명령의 콘솔 출력에 다음 정보를 포함하는 목록이 표시됩니다. 리포지토리, 태그, 이미지 ID, 만든 날짜 및 크기](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-images-command.png)

**그림 4-45**. Docker 이미지 보기

## <a name="register-the-solution-in-an-azure-container-registry-acr"></a>ACR(Azure Container Registry)에 솔루션 등록

ACR([Azure Container Registry](https://azure.microsoft.com/services/container-registry/))에 이미지를 업로드할 수 있지만 Docker Hub 또는 다른 레지스트리를 사용할 수도 있으므로 해당 레지스트리에서 AKS 클러스터에 이미지를 배포할 수 있습니다.

### <a name="create-an-acr-instance"></a>ACR 인스턴스 만들기

**az cli**에서 다음 명령을 실행합니다.

```powershell
az acr create --name exploredocker --resource-group explore-docker-aks-rg --sku basic --admin-enabled
```

### <a name="create-the-image-in-release-mode"></a>릴리스 모드에서 이미지 만들기

이제 그림 4-46과 같이 **릴리스**로 변경하고 이전과 같은 방법으로 애플리케이션을 실행하여 **릴리스** 모드에서 (프로덕션 준비가 완료된) 이미지를 만듭니다.

![릴리스 모드에서 빌드하기 위한 VS의 도구 모음 옵션](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-release-mode.png)

**그림 4-46**. 릴리스 모드 선택

`docker images` 명령을 실행하면 `debug`용(**dev**) 이미지 1개와 `release`용(**latest**) 이미지 1개로 이루어진 2개의 이미지가 만들어집니다.

### <a name="create-a-new-tag-for-the-image"></a>이미지에 대한 새 태그 만들기

각 컨테이너 이미지에 레지스트리의 `loginServer` 이름으로 태그를 지정해야 합니다. 이 태그는 컨테이너 이미지를 이미지 레지스트리에 밀어넣을 때 라우팅에 사용됩니다.

Azure Portal에서 `loginServer` 이름을 보고 Azure Container Registry에서 정보를 가져올 수 있습니다.

![브라우저 오른쪽 위의 Azure 컨테이너 레지스트리 이름 보기](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/loginServer-name.png)

**그림 4-47**. 레지스트리의 이름 보기

또는 다음 명령을 실행하여 이름을 봅니다.

```console
az acr list --resource-group <resource-group-name> --query "[].{acrLoginServer:loginServer}" --output table
```

![위 명령의 콘솔 출력](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/az-cli-loginServer-name.png)

**그림 4-48**. **az cli**를 사용하여 레지스트리의 이름 가져오기

두 경우 모두 이름을 가져옵니다. 이 예제의 경우 이름은 `exploredocker.azurecr.io`입니다.

이제 다음 명령을 사용하여 이미지에 태그를 지정하고 최신 이미지를 가져올 수 있습니다.

```console
docker tag <image-name>:latest <login-server-name>/<image-name>:v1
```

`docker tag` 명령을 실행한 후 `docker images` 명령을 사용하여 이미지를 나열하면 새 태그가 지정된 이미지가 보일 것입니다.

![Docker 이미지 명령의 콘솔 출력](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/tagged-docker-images-list.png)

**그림 4-49**. 태그가 지정된 이미지 보기

### <a name="push-the-image-into-the-azure-acr"></a>Azure ACR에 이미지 푸시

Azure Container Registry에 로그인합니다.

```console
az acr login --name exploredocker
```

다음 명령을 사용하여 이미지를 Azure ACR에 푸시합니다.

```console
docker push <login-server-name>/<image-name>:v1
```

이 명령은 이미지를 업로드하는 동안 다소 시간이 걸리지만 프로세스와 관련된 피드백을 제공합니다. 다음 이미지에서는 한 이미지는 완료되고 다른 이미지는 진행 중일 때의 출력을 볼 수 있습니다.

![docker push 명령의 콘솔 출력입니다.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/uploading-docker-images-complete.png)

**그림 4-50**. push 명령의 콘솔 출력.

다중 컨테이너 앱을 AKS 클러스터에 배포하려면 대부분의 속성을 `docker-compose.yml` 및 `docker-compose.override.yml` 파일에서 가져오는 일부 매니페스트 `.yaml` 파일이 필요합니다.

#### `deploy-webapi.yml`

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapi
  labels:
    app: weather-forecast
spec:
  replicas: 1
  selector:
    matchLabels:
      service: webapi
  template:
    metadata:
      labels:
        app: weather-forecast
        service: webapi
    spec:
      containers:
        - name: webapi
          image: exploredocker.azurecr.io/webapi:v1
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 80
              protocol: TCP
          env:
            - name: ASPNETCORE_URLS
              value: http://+:80
---
apiVersion: v1
kind: Service
metadata:
  name: webapi
  labels:
    app: weather-forecast
    service: webapi
spec:
  ports:
    - port: 80
      targetPort: 80
      protocol: TCP
  selector:
    service: webapi
```

#### `deploy-webapp.yml`

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapp
  labels:
    app: weather-forecast
spec:
  replicas: 1
  selector:
    matchLabels:
      service: webapp
  template:
    metadata:
      labels:
        app: weather-forecast
        service: webapp
    spec:
      containers:
        - name: webapp
          image: exploredocker.azurecr.io/webapp:v1
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 80
              protocol: TCP
          env:
            - name: ASPNETCORE_URLS
              value: http://+:80
            - name: WebApiBaseAddress
              value: http://webapi
---
apiVersion: v1
kind: Service
metadata:
  name: webapp
  labels:
    app: weather-forecast
    service: webapp
spec:
  type: LoadBalancer
  ports:
    - port: 80
      targetPort: 80
      protocol: TCP
  selector:
    service: webapp
```

> [!NOTE]
> 이전 `.yml` 파일은 `ASPNETCORE_URLS` 매개 변수를 사용하여 `HTTP` 포트만 사용하도록 설정하여 샘플 앱에서 누락된 인증서와 관련된 문제가 발생하지 않도록 합니다.

> [!TIP]
> 이 가이드의 [**AKS(Azure Kubernetes Service)에 배포**](deploy-azure-kubernetes-service.md) 섹션에서 이 샘플에 대한 AKS 클러스터를 만드는 방법을 확인할 수 있습니다.

이제 **kubectl**을 사용하여 배포할 준비가 거의 완료되었지만 먼저 이 명령을 사용하여 AKS 클러스터에서 자격 증명을 가져와야 합니다.

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![위 명령의 콘솔 출력: C:\Users\Miguel.kube\config에서 “explore-docker-aks”가 현재 컨텍스트로 병합됩니다.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/getting-aks-credentials.png)

**그림 4-51**. AKS에서 kubectl 환경으로 자격 증명 가져오기.

또한 다음 명령을 사용하여 AKS 클러스터가 ACR에서 이미지를 끌어올 수 있도록 해야 합니다.

```console
az aks update --name explore-docker-aks --resource-group explore-docker-aks-rg --attach-acr exploredocker
```

이전 명령은 완료하는 데 몇 분 정도 걸릴 수 있습니다. 그런 다음, `kubectl apply` 명령을 사용하여 배포를 시작한 다음, `kubectl get all` 명령을 사용하여 클러스터 개체 목록을 가져옵니다.

```console
kubectl apply -f deploy-webapi.yml
kubectl apply -f deploy-webapp.yml

kubectl get all
```

![위 명령의 콘솔 출력: 배포를 적용함. 서비스를 생성함.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubectl-apply-command.png)

**그림 4-52**. Kubernetes에 배포

다음 이미지에 표시된 것처럼 부하 분산 장치에서 외부 IP를 가져올 때까지 잠시 기다렸다가 `kubectl get services`를 사용하여 확인합니다. 그러면 해당 주소에서 애플리케이션을 사용할 수 있습니다.

![AKS에 배포된 애플리케이션의 브라우저 보기](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/aks-deployed-application.png)

**그림 4-53**. Kubernetes에 배포

배포가 완료되면 ssh 터널을 사용하여 로컬 프록시를 통해 [Kubernetes 웹 UI](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/)에 액세스할 수 있습니다.

먼저 다음 명령을 사용하여 ClusterRoleBinding을 만들어야 합니다.

```console
kubectl create clusterrolebinding kubernetes-dashboard --clusterrole=cluster-admin --serviceaccount=kube-system:kubernetes-dashboard
```

그런 다음, 이 명령을 실행하여 프록시를 시작합니다.

```console
az aks browse --resource-group exploredocker-aks-rg --name explore-docker-aks
```

브라우저 창이 다음과 비슷한 보기로 `http://127.0.0.1:8001`에서 열립니다.

![배포, Pod, 복제본 세트 및 서비스를 보여주는 Kubernetes 대시보드의 브라우저 보기](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubernetes-cluster-information.png)

**그림 4-54**. Kubernetes 클러스터 정보 보기

이제 ASP.NET Core 애플리케이션이 Linux 컨테이너에서 실행되며, Azure의 AKS 클러스터에 배포되었습니다.

> [!NOTE]
> Kubernetes를 사용한 배포에 대한 자세한 내용은 <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>를 참조하세요.

> [!div class="step-by-step"]
> [이전](set-up-windows-containers-with-powershell.md)
> [다음](../docker-devops-workflow/index.md)

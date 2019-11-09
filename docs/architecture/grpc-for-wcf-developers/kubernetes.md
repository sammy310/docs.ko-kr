---
title: WCF 개발자를 위한 Kubernetes (gRPC)
description: Kubernetes 클러스터에서 ASP.NET Core gRPC 서비스를 실행 하 고 있습니다.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 819c761a7a55485612b7fb0c8b392971751d8724
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841578"
---
# <a name="kubernetes"></a><span data-ttu-id="4ae98-103">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="4ae98-103">Kubernetes</span></span>

<span data-ttu-id="4ae98-104">Docker 호스트에서 수동으로 컨테이너를 실행할 수 있지만 신뢰할 수 있는 프로덕션 시스템에서는 컨테이너 오케스트레이션 엔진을 사용 하 여 클러스터의 여러 서버에서 실행 되는 여러 인스턴스를 관리 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-104">Although it's possible to run containers manually on Docker hosts, for reliable production systems it's preferable to use a Container Orchestration Engine to manage multiple instances running across several servers in a cluster.</span></span> <span data-ttu-id="4ae98-105">Kubernetes, Docker Swarm 및 Apache Mesos를 포함 하 여 다양 한 컨테이너 오케스트레이션 엔진을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-105">There are various Container Orchestration Engines available, including Kubernetes, Docker Swarm and Apache Mesos.</span></span> <span data-ttu-id="4ae98-106">그러나 이러한 엔진은 Kubernetes이 가장 널리 사용 되는 것 이므로이 챕터에 중점을 두고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-106">But of these engines, Kubernetes is far and away the most widely used, so it will be the focus of this chapter.</span></span>

<span data-ttu-id="4ae98-107">Kubernetes에는 다음과 같은 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-107">Kubernetes includes the following functionality:</span></span>

- <span data-ttu-id="4ae98-108">**일정** 은 클러스터 내의 여러 노드에서 컨테이너를 실행 하 고, 사용 가능한 리소스의 균형을 유지 하 고, 중단이 발생 한 경우 컨테이너를 실행 하 고, 새 버전의 이미지 또는 새 구성에 대 한 롤링 업데이트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-108">**Scheduling** runs containers on multiple nodes within a cluster, ensuring balanced usage of the available resource, keeping containers running if there are outages, and handling rolling updates to new versions of images or new configurations.</span></span>
- <span data-ttu-id="4ae98-109">**상태 검사** 는 컨테이너를 모니터링 하 여 계속 서비스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-109">**Health checks** monitor containers to ensure continued service.</span></span>
- <span data-ttu-id="4ae98-110">**DNS & 서비스 검색** 은 클러스터 내의 서비스 간 라우팅을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-110">**DNS & service discovery** handles routing between services within a cluster.</span></span>
- <span data-ttu-id="4ae98-111">**수신** 은 선택한 서비스를 외부적으로 노출 하 고, 일반적으로 해당 서비스의 인스턴스 간에 부하 분산을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-111">**Ingress** exposes selected services externally, and generally provides load-balancing across instances of those services.</span></span>
- <span data-ttu-id="4ae98-112">**리소스 관리** 는 저장소와 같은 외부 리소스를 컨테이너에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-112">**Resource management** attaches external resources such as storage to containers.</span></span>

<span data-ttu-id="4ae98-113">이 장에서는 ASP.NET Core gRPC 서비스를 배포 하는 방법 및 서비스를 사용 하는 웹 사이트를 Kubernetes 클러스터에 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-113">This chapter will detail how to deploy an ASP.NET Core gRPC service and a website that consumes the service into a Kubernetes cluster.</span></span> <span data-ttu-id="4ae98-114">사용 되는 샘플 응용 프로그램은 GitHub의 [dotnet-아키텍처/grpc-wcf-개발자](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) 리포지토리의에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-114">The sample application used is available from on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub,</span></span>

## <a name="kubernetes-terminology"></a><span data-ttu-id="4ae98-115">Kubernetes 용어</span><span class="sxs-lookup"><span data-stu-id="4ae98-115">Kubernetes terminology</span></span>

<span data-ttu-id="4ae98-116">Kubernetes는 *필요한 상태 구성을*사용 합니다. API는 *pod*, *배포* 및 *서비스*와 같은 개체를 설명 하는 데 사용 되 고, *제어 평면은* *클러스터*의 모든 *노드에* 대해 원하는 상태를 구현 하는 작업을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-116">Kubernetes uses *desired state configuration*: the API is used to describe objects such as *Pods*, *Deployments* and *Services*, and the *Control Plane* takes care of implementing the desired state across all the *nodes* in a *cluster*.</span></span> <span data-ttu-id="4ae98-117">Kubernetes 클러스터에는 프로그래밍 방식으로 또는 `kubectl` 명령줄 도구를 사용 하 여 통신할 수 있는 *KUBERNETES API*를 실행 하는 *마스터* 노드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-117">A Kubernetes cluster has a *Master* node that runs the *Kubernetes API*, which can be communicated with programmatically or using the `kubectl` command-line tool.</span></span> <span data-ttu-id="4ae98-118">`kubectl`는 명령줄 인수를 사용 하 여 개체를 만들고 관리할 수 있지만 Kubernetes 개체에 대 한 선언 데이터를 포함 하는 YAML 파일에서 가장 잘 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-118">`kubectl` can create and manage objects using command-line arguments, but works best with YAML files that contain declaration data for Kubernetes objects.</span></span>

### <a name="kubernetes-yaml-files"></a><span data-ttu-id="4ae98-119">Kubernetes YAML 파일</span><span class="sxs-lookup"><span data-stu-id="4ae98-119">Kubernetes YAML files</span></span>

<span data-ttu-id="4ae98-120">모든 Kubernetes YAML 파일에는 세 개 이상의 최상위 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-120">Every Kubernetes YAML file will have at least three top-level properties.</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  # Object properties
```

<span data-ttu-id="4ae98-121">`apiVersion` 속성은 파일에 사용할 버전 (및 API)을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-121">The `apiVersion` property is used to specify which version (and which API) the file is intended for.</span></span> <span data-ttu-id="4ae98-122">`kind` 속성은 YAML가 나타내는 개체의 종류를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-122">The `kind` property specifies the kind of object the YAML represents.</span></span> <span data-ttu-id="4ae98-123">`metadata` 속성에는 `name`, `namespace`또는 `labels`같은 개체 속성이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-123">The `metadata` property contains object properties such as `name`, `namespace`, or `labels`.</span></span>

<span data-ttu-id="4ae98-124">대부분의 Kubernetes YAML 파일에는 개체를 만드는 데 필요한 리소스와 구성을 설명 하는 `spec` 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-124">Most Kubernetes YAML files will also have a `spec` section that describes the resources and configuration necessary to create the object.</span></span>

### <a name="pods"></a><span data-ttu-id="4ae98-125">pod</span><span class="sxs-lookup"><span data-stu-id="4ae98-125">Pods</span></span>

<span data-ttu-id="4ae98-126">Pod는 Kubernetes의 기본 실행 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-126">Pods are the basic units of execution in Kubernetes.</span></span> <span data-ttu-id="4ae98-127">여러 컨테이너를 실행할 수 있지만 단일 컨테이너를 실행 하는 데도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-127">They can run multiple containers, but are also used to run single containers.</span></span> <span data-ttu-id="4ae98-128">Pod에는 컨테이너에 필요한 저장소 리소스와 네트워크 IP 주소도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-128">The pod also includes any storage resources required by the container(s), and the network IP address.</span></span>

### <a name="services"></a><span data-ttu-id="4ae98-129">서비스</span><span class="sxs-lookup"><span data-stu-id="4ae98-129">Services</span></span>

<span data-ttu-id="4ae98-130">서비스는 pod (또는 pod 집합)를 설명 하 고 클러스터 내에서이를 액세스 하는 방법을 제공 하는 메타 개체입니다. 예를 들어 클러스터 DNS 서비스를 사용 하 여 pod IP 주소 집합에 서비스 이름을 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-130">Services are meta-objects that describe pods (or sets of pods) and provide a way to access them within the cluster, such as mapping a service name to a set of pod IP addresses using the cluster DNS service.</span></span>

### <a name="deployments"></a><span data-ttu-id="4ae98-131">배포</span><span class="sxs-lookup"><span data-stu-id="4ae98-131">Deployments</span></span>

<span data-ttu-id="4ae98-132">배포는 Pod에 대해 *설명 된 상태* 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-132">Deployments are the *described state* objects for Pods.</span></span> <span data-ttu-id="4ae98-133">Pod를 수동으로 만드는 경우에는 종료 될 때 다시 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-133">If you create a Pod manually, when it terminates it won't be restarted.</span></span> <span data-ttu-id="4ae98-134">배포를 사용 하 여 클러스터에 pod 하 고 현재 해당 pod 복제본의 수를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-134">Deployments are used to tell the cluster which pods, and how many replicas of those pods, should be running at the present time.</span></span>

### <a name="other-objects"></a><span data-ttu-id="4ae98-135">기타 개체</span><span class="sxs-lookup"><span data-stu-id="4ae98-135">Other objects</span></span>

<span data-ttu-id="4ae98-136">Pod, 서비스 및 배포는 가장 기본적인 개체 유형 중 세 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-136">Pods, Services, and Deployments are just three of the most basic object types.</span></span> <span data-ttu-id="4ae98-137">Kubernetes 클러스터에서 관리 하는 다양 한 형식의 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-137">There are dozens of other types of object that are managed by a Kubernetes cluster.</span></span> <span data-ttu-id="4ae98-138">자세한 내용은 [Kubernetes 개념](https://kubernetes.io/docs/concepts/) 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ae98-138">For more information, see the [Kubernetes Concepts](https://kubernetes.io/docs/concepts/) documentation.</span></span>

### <a name="namespaces"></a><span data-ttu-id="4ae98-139">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="4ae98-139">Namespaces</span></span>

<span data-ttu-id="4ae98-140">Kubernetes 클러스터는 수백 또는 수천 개의 노드로 확장 하 고 비슷한 수의 서비스를 실행 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-140">Kubernetes clusters are designed to scale to hundreds or thousands of nodes, and run similar numbers of services.</span></span> <span data-ttu-id="4ae98-141">개체 이름 간에 충돌을 방지 하기 위해 네임 스페이스를 사용 하 여 더 큰 응용 프로그램의 일부로 개체를 그룹화 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-141">To avoid clashes between object names, namespaces are used to group objects together as part of larger applications.</span></span> <span data-ttu-id="4ae98-142">Kubernetes 자체 서비스는 `default` 네임 스페이스에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-142">Kubernetes own services run in a `default` namespace.</span></span> <span data-ttu-id="4ae98-143">기본 개체 또는 클러스터의 다른 테 넌 트가 충돌 하는 경우를 방지 하기 위해 모든 사용자 개체를 고유한 네임 스페이스에 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-143">All user objects should be created in their own namespaces to avoid potential clashes with default objects or other tenants in the cluster.</span></span>

## <a name="get-started-with-kubernetes"></a><span data-ttu-id="4ae98-144">Kubernetes 시작</span><span class="sxs-lookup"><span data-stu-id="4ae98-144">Get started with Kubernetes</span></span>

<span data-ttu-id="4ae98-145">Docker Desktop for Windows 또는 macOS를 실행 하는 경우 Kubernetes를 이미 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-145">If you're running Docker Desktop for Windows or macOS, Kubernetes is already available.</span></span> <span data-ttu-id="4ae98-146">설정 창의 Kubernetes 섹션에서 사용 하도록 설정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-146">Just enable it in the Kubernetes section of the Settings window.</span></span>

![Docker Desktop에서 Kubernetes 사용](media/kubernetes/enable-kubernetes-docker-desktop.png)

<span data-ttu-id="4ae98-148">Linux에서 로컬 Kubernetes 클러스터를 실행 하려면 Linux 배포판에서 [스냅](https://snapcraft.io/)을 지 원하는 경우 [minikube](https://github.com/kubernetes/minikube)또는 [MicroK8s](https://microk8s.io/) 를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="4ae98-148">To run a local Kubernetes cluster in Linux, look at [minikube](https://github.com/kubernetes/minikube), or [MicroK8s](https://microk8s.io/) if your Linux distribution supports [snaps](https://snapcraft.io/).</span></span>

<span data-ttu-id="4ae98-149">클러스터가 실행 중이 고 액세스 가능한 지 확인 하려면 `kubectl version` 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-149">To check that your cluster is running and accessible, run the `kubectl version` command.</span></span>

```console
kubectl version
Client Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:13:49Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"windows/amd64"}
Server Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:05:16Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"linux/amd64"}
```

<span data-ttu-id="4ae98-150">이 예제에서는 `kubectl` CLI와 Kubernetes 서버 모두 버전 1.14.6를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-150">In this example, both the `kubectl` CLI and the Kubernetes server are running version 1.14.6.</span></span> <span data-ttu-id="4ae98-151">`kubectl`의 각 버전은 이전 및 다음 버전의 서버를 지원 해야 하므로 1.14 `kubectl` 서버 버전 1.13 및 1.15 에서도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-151">Each version of `kubectl` is supposed to support the previous and next version of the server, so `kubectl` 1.14 should work with server versions 1.13 and 1.15 as well.</span></span>

## <a name="run-services-on-kubernetes"></a><span data-ttu-id="4ae98-152">Kubernetes에서 서비스 실행</span><span class="sxs-lookup"><span data-stu-id="4ae98-152">Run services on Kubernetes</span></span>

<span data-ttu-id="4ae98-153">샘플 응용 프로그램에는 3 개의 YAML 파일이 포함 된 `kube` 디렉터리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-153">The sample application has a `kube` directory containing three YAML files.</span></span> <span data-ttu-id="4ae98-154">`namespace.yml` 파일은 사용자 지정 네임 스페이스 `stocks`를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-154">The `namespace.yml` file declares a custom namespace, `stocks`.</span></span> <span data-ttu-id="4ae98-155">`stockdata.yml` 파일은 gRPC 응용 프로그램에 대 한 배포 및 서비스를 선언 하 고, `stockweb.yml` 파일은 gRPC 서비스를 사용 하는 ASP.NET Core 3.0 MVC 웹 응용 프로그램에 대 한 배포 및 서비스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-155">The `stockdata.yml` file declares the Deployment and the Service for the gRPC application, and the `stockweb.yml` file declares the Deployment and Service for an ASP.NET Core 3.0 MVC web application that consumes the gRPC service.</span></span>

<span data-ttu-id="4ae98-156">`kubectl`에서 `YAML` 파일을 사용 하려면 `apply -f` 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-156">To use a `YAML` file with `kubectl`, use the `apply -f` command.</span></span>

```console
kubectl apply -f object.yml
```

<span data-ttu-id="4ae98-157">`apply` 명령은 YAML 파일의 유효성을 검사 하 고 API에서 받은 모든 오류를 표시 하지만, 파일에 선언 된 모든 개체를 만들 때까지 기다리지 않습니다 .이는 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-157">The `apply` command will check the validity of the YAML file and display any errors received from the API, but doesn't wait until all the objects declared in the file have been created as this can take some time.</span></span> <span data-ttu-id="4ae98-158">관련 개체 유형과 함께 `kubectl get` 명령을 사용 하 여 클러스터의 개체 생성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-158">Use the `kubectl get` command with the relevant object types to check on object creation in the cluster.</span></span>

### <a name="the-namespace-declaration"></a><span data-ttu-id="4ae98-159">네임 스페이스 선언</span><span class="sxs-lookup"><span data-stu-id="4ae98-159">The namespace declaration</span></span>

<span data-ttu-id="4ae98-160">네임 스페이스 선언은 간단 하며 `name`할당 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-160">Namespace declaration is simple and requires only assigning a `name`.</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: stocks
```

<span data-ttu-id="4ae98-161">`kubectl`를 사용 하 여 `namespace.yml` 파일을 적용 하 고 네임 스페이스가 성공적으로 만들어졌는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-161">Use `kubectl` to apply the `namespace.yml` file and check the namespace is created successfully.</span></span>

```console
> kubectl apply -f namespace.yml
namespace/stocks created

> kubectl get namespaces
NAME              STATUS   AGE
stocks            Active   2m53s
```

### <a name="the-stockdata-application"></a><span data-ttu-id="4ae98-162">StockData 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="4ae98-162">The StockData application</span></span>

<span data-ttu-id="4ae98-163">`stockdata.yml` 파일은 배포 및 서비스의 두 개체를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-163">The `stockdata.yml` file declares two objects: a Deployment and a Service.</span></span>

#### <a name="the-stockdata-deployment"></a><span data-ttu-id="4ae98-164">StockData 배포</span><span class="sxs-lookup"><span data-stu-id="4ae98-164">The StockData Deployment</span></span>

<span data-ttu-id="4ae98-165">배포 파트는 배포에 필요한 복제본 수를 비롯 하 여 배포 자체에 대 한 `spec`를 제공 하 고, 배포에서 만들고 관리 하는 Pod 개체에 대 한 `template`를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-165">The Deployment part provides the `spec` for the deployment itself, including the number of replicas required, and a `template` for the Pod objects to be created and managed by the deployment.</span></span> <span data-ttu-id="4ae98-166">배포 개체는 주 Kubernetes API가 아닌 `apiVersion`에 지정 된 `apps` API를 사용 하 여 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-166">Note that Deployment objects are managed with the `apps` API, as specified in `apiVersion`, rather than the main Kubernetes API.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockdata
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockdata
  replicas: 1
  template:
    metadata:
      labels:
        run: stockdata
    spec:
      containers:
      - name: stockdata
        image: stockdata:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
```

<span data-ttu-id="4ae98-167">`spec.selector` 속성은 실행 중인 Pod를 배포에 일치 시키는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-167">The `spec.selector` property is used to match running Pods to the Deployment.</span></span> <span data-ttu-id="4ae98-168">Pod의 `metadata.labels` 속성은 `matchLabels` 속성과 일치 해야 합니다. 그렇지 않으면 API 호출이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-168">The Pod's `metadata.labels` property must match the `matchLabels` property or the API call will fail.</span></span>

<span data-ttu-id="4ae98-169">`template.spec` 섹션에서는 실행할 컨테이너를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-169">The `template.spec` section declares the container to be run.</span></span> <span data-ttu-id="4ae98-170">Docker Desktop에서 제공 하는 것과 같은 로컬 Kubernetes 클러스터를 사용 하는 경우 버전 태그가 있는 한 로컬로 빌드된 이미지를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-170">When working with a local Kubernetes cluster, such as the one provided by Docker Desktop, you can specify images that were built locally as long as they have a version tag.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ae98-171">기본적으로 Kubernetes는 항상 새 이미지를 확인 하 고 가져오려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-171">By default, Kubernetes will always check for and try to pull a new image.</span></span> <span data-ttu-id="4ae98-172">알려진 리포지토리에서 이미지를 찾을 수 없는 경우 Pod 생성은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-172">If it can't find the image in any of its known repositories, the Pod creation will fail.</span></span> <span data-ttu-id="4ae98-173">로컬 이미지를 사용 하려면 `imagePullPolicy` `Never`으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-173">To work with local images, set the `imagePullPolicy` to `Never`.</span></span>

<span data-ttu-id="4ae98-174">`ports` 속성은 Pod에 게시할 컨테이너 포트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-174">The `ports` property specifies which container ports should be published on the Pod.</span></span>  <span data-ttu-id="4ae98-175">`stockservice` 이미지는 표준 HTTP 포트에서 서비스를 실행 하므로 포트 80이 게시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-175">The `stockservice` image runs the service on the standard HTTP port, so port 80 is published.</span></span>

<span data-ttu-id="4ae98-176">`resources` 섹션에서는 pod 내에서 실행 중인 컨테이너에 리소스 제한을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-176">The `resources` section applies resource limits to the container running within the pod.</span></span> <span data-ttu-id="4ae98-177">이 방법은 개별 pod가 노드에서 사용 가능한 모든 CPU 또는 메모리를 사용 하지 못하도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-177">This is good practice as it prevents an individual pod from consuming all the available CPU or memory on a node.</span></span>

> [!NOTE]
> <span data-ttu-id="4ae98-178">ASP.NET Core 3.0은 리소스 제한 컨테이너에서 실행 되도록 최적화 및 조정 되었으며 `dotnet/core/aspnet` Docker 이미지는 환경 변수를 설정 하 여 `dotnet` 런타임에 컨테이너에 있음을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-178">ASP.NET Core 3.0 has been optimized and tuned to run in resource-limited containers, and the `dotnet/core/aspnet` Docker image sets an environment variable to tell the `dotnet` runtime that it's in a container.</span></span>

#### <a name="the-stockdata-service"></a><span data-ttu-id="4ae98-179">StockData 서비스</span><span class="sxs-lookup"><span data-stu-id="4ae98-179">The StockData Service</span></span>

<span data-ttu-id="4ae98-180">YAML 파일의 서비스 부분은 클러스터 내의 Pod에 대 한 액세스를 제공 하는 서비스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-180">The Service part of the YAML file declares the service that provides access to the Pods within the cluster.</span></span>

```yaml
apiVersion: v1
kind: Service
metadata:
  name: stockdata
  namespace: stocks
spec:
  ports:
  - port: 80
  selector:
    run: stockdata
```

<span data-ttu-id="4ae98-181">서비스 사양은 `selector` 속성을 사용 하 여 실행 중인 `Pods`일치 시킵니다 .이 경우 레이블이 `run: stockdata`인 Pod을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-181">The Service spec uses the `selector` property to match running `Pods`, in this case looking for Pods with a label `run: stockdata`.</span></span> <span data-ttu-id="4ae98-182">일치 하는 Pod에 지정 된 `port`은 명명 된 서비스에 의해 게시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-182">The specified `port` on matching Pods are published by the named service.</span></span> <span data-ttu-id="4ae98-183">`stocks` 네임 스페이스에서 실행 되는 다른 Pod는 `http://stockdata` 주소를 사용 하 여이 서비스의 HTTP에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-183">Other Pods running in the `stocks` namespace can access HTTP on this service using `http://stockdata` as the address.</span></span> <span data-ttu-id="4ae98-184">다른 네임 스페이스에서 실행 되는 pod는 `http://stockdata.stocks` 호스트 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-184">Pods running in other namespaces can use the `http://stockdata.stocks` hostname.</span></span> <span data-ttu-id="4ae98-185">[네트워크 정책을](https://kubernetes.io/docs/concepts/services-networking/network-policies/)사용 하 여 네임 스페이스 간 서비스 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-185">You can control cross-namespace service access using [Network Policies](https://kubernetes.io/docs/concepts/services-networking/network-policies/).</span></span>

#### <a name="deploy-the-stockdata-application"></a><span data-ttu-id="4ae98-186">StockData 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="4ae98-186">Deploy the StockData application</span></span>

<span data-ttu-id="4ae98-187">`kubectl`를 사용 하 여 `stockdata.yml` 파일을 적용 하 고 배포 및 서비스를 만들었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-187">Use `kubectl` to apply the `stockdata.yml` file and check that the Deployment and Service were created.</span></span>

```console
> kubectl apply -f .\stockdata.yml
deployment.apps/stockdata created
service/stockdata created

> kubectl get deployment stockdata --namespace stocks
NAME        READY   UP-TO-DATE   AVAILABLE   AGE
stockdata   1/1     1            1           17s

> kubectl get service stockdata --namespace stocks
NAME        TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)   AGE
stockdata   ClusterIP   10.97.132.103   <none>        80/TCP    33s
```

### <a name="the-stockweb-application"></a><span data-ttu-id="4ae98-188">StockWeb 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="4ae98-188">The StockWeb application</span></span>

<span data-ttu-id="4ae98-189">`stockweb.yml` 파일은 MVC 응용 프로그램에 대 한 배포 및 서비스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-189">The `stockweb.yml` file declares the Deployment and Service for the MVC application.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockweb
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockweb
  replicas: 1
  template:
    metadata:
      labels:
        run: stockweb
    spec:
      containers:
      - name: stockweb
        image: stockweb:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
        env:
        - name: StockData__Address
          value: "http://stockdata"
        - name: DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT
          value: "true"

---

apiVersion: v1
kind: Service
metadata:
  name: stockweb
  namespace: stocks
spec:
  type: NodePort
  ports:
  - port: 80
  selector:
    run: stockweb
```

#### <a name="environment-variables"></a><span data-ttu-id="4ae98-190">환경 변수</span><span class="sxs-lookup"><span data-stu-id="4ae98-190">Environment variables</span></span>

<span data-ttu-id="4ae98-191">배포 개체의 `env` 섹션에서는 `stockweb:1.0.0` 이미지를 실행 하는 컨테이너에 설정할 환경 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-191">The `env` section of the Deployment object specifies environment variables to be set in the container running the `stockweb:1.0.0` images.</span></span>

<span data-ttu-id="4ae98-192">**`StockData__Address`** 환경 변수는 환경 변수 구성 공급자 덕분에 `StockData:Address` 구성 설정에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-192">The **`StockData__Address`** environment variable will map to the `StockData:Address` configuration setting thanks to the EnvironmentVariables configuration provider.</span></span> <span data-ttu-id="4ae98-193">이 설정은 이름 사이에 두 개의 밑줄을 사용 하 여 섹션을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-193">This setting uses double underscores between names to separate sections.</span></span> <span data-ttu-id="4ae98-194">주소는 동일한 Kubernetes 네임 스페이스에서 실행 되는 `stockdata` 서비스의 서비스 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-194">The address uses the service name of the `stockdata` Service, which is running in the same Kubernetes namespace.</span></span>

<span data-ttu-id="4ae98-195">**`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** 환경 변수는 <xref:System.Net.Http.HttpClient>에 대해 암호화 되지 않은 HTTP/2 연결을 사용 하도록 설정 하는 <xref:System.AppContext> 스위치를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-195">The **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** environment variable sets an <xref:System.AppContext> switch that enables unencrypted HTTP/2 connections for <xref:System.Net.Http.HttpClient>.</span></span> <span data-ttu-id="4ae98-196">이 환경 변수는 여기에 표시 된 대로 코드에서 스위치를 설정 하는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-196">This environment variable is the equivalent of setting the switch in code as shown here.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="4ae98-197">스위치에 대 한 환경 변수를 사용 하면 응용 프로그램이 실행 되는 컨텍스트에 따라 설정을 쉽게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-197">Using an environment variable for the switch means the setting can easily be changed depending on the context in which the application is running.</span></span>

#### <a name="service-types"></a><span data-ttu-id="4ae98-198">서비스 유형</span><span class="sxs-lookup"><span data-stu-id="4ae98-198">Service types</span></span>

<span data-ttu-id="4ae98-199">클러스터 외부에서 웹 응용 프로그램에 액세스할 수 있도록 `type: NodePort` 속성이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-199">To make the Web application accessible from outside the cluster, the `type: NodePort` property is used.</span></span> <span data-ttu-id="4ae98-200">이 속성 형식을 통해 Kubernetes는 서비스의 포트 80을 클러스터의 외부 네트워크 소켓에 있는 임의의 포트에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-200">This property type causes Kubernetes to publish port 80 on the Service to an arbitrary port on the cluster's external network sockets.</span></span> <span data-ttu-id="4ae98-201">할당 된 포트는 `kubectl get service` 명령을 사용 하 여 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-201">The port assigned can be found using the `kubectl get service` command.</span></span>

<span data-ttu-id="4ae98-202">`stockdata` 서비스는 클러스터 외부에서 액세스할 수 없으므로 기본 유형인 `ClusterIP`를 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-202">The `stockdata` service shouldn't be accessible from outside the cluster, so it used the default type, `ClusterIP`.</span></span>

<span data-ttu-id="4ae98-203">프로덕션 시스템은 공용 응용 프로그램을 외부 소비자에 게 노출 하기 위해 통합 된 부하 분산 장치를 사용 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-203">Production systems will most likely use an integrated load-balancer to expose public applications to external consumers.</span></span> <span data-ttu-id="4ae98-204">이러한 방식으로 노출 되는 서비스는 `LoadBalancer` 형식을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-204">Services exposed in this way should use the `LoadBalancer` type.</span></span>

<span data-ttu-id="4ae98-205">서비스 유형에 대 한 자세한 내용은 [Kubernetes의 Publishing Services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ae98-205">For more information on service types, see the [Kubernetes' Publishing Services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) documentation.</span></span>

#### <a name="deploy-the-stockweb-application"></a><span data-ttu-id="4ae98-206">StockWeb 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="4ae98-206">Deploy the StockWeb application</span></span>

<span data-ttu-id="4ae98-207">`kubectl`를 사용 하 여 `stockweb.yml` 파일을 적용 하 고 배포 및 서비스를 만들었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-207">Use `kubectl` to apply the `stockweb.yml` file and check that the Deployment and Service were created.</span></span>

```console
> kubectl apply -f .\stockweb.yml
deployment.apps/stockweb created
service/stockweb created

> kubectl get deployment stockweb --namespace stocks
NAME       READY   UP-TO-DATE   AVAILABLE   AGE
stockweb   1/1     1            1           8s

> kubectl get service stockweb --namespace stocks
NAME       TYPE       CLUSTER-IP     EXTERNAL-IP   PORT(S)        AGE
stockweb   NodePort   10.106.141.5   <none>        80:32564/TCP   13s
```

<span data-ttu-id="4ae98-208">`get service` 명령의 출력은 HTTP 포트가 외부 네트워크의 포트 `32564`에 게시 되었음을 보여 줍니다. Docker 데스크톱의 경우 localhost가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-208">The output from the `get service` command shows that the HTTP port has been published to port `32564` on the external network; for Docker Desktop, this will be localhost.</span></span> <span data-ttu-id="4ae98-209">`http://localhost:32564`를 검색 하 여 응용 프로그램에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-209">The application can be accessed by browsing to `http://localhost:32564`.</span></span>

### <a name="testing-the-application"></a><span data-ttu-id="4ae98-210">애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="4ae98-210">Testing the application</span></span>

<span data-ttu-id="4ae98-211">StockWeb 응용 프로그램은 간단한 요청-회신 서비스에서 검색 된 NASDAQ 주식 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-211">The StockWeb application displays a list of NASDAQ stocks that are retrieved from a simple request-reply service.</span></span> <span data-ttu-id="4ae98-212">데모용으로 각 줄에는 반환 된 서비스 인스턴스의 고유 ID도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-212">For demonstration purposes, each line also shows the unique ID of the service instance that returned it.</span></span>

![StockWeb 스크린 샷](media/kubernetes/stockweb-screenshot.png)

<span data-ttu-id="4ae98-214">`stockdata` 서비스의 복제본 수가 증가 한 경우 **서버** 값이 줄에서 줄로 변경 될 수 있지만 실제로 모든 100 레코드는 동일한 인스턴스에서 항상 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-214">If the number of replicas of the `stockdata` service were increased, you might expect the **Server** value to change from line to line, but in fact all 100 records are always returned from the same instance.</span></span> <span data-ttu-id="4ae98-215">몇 초 마다 페이지를 새로 고치면 서버 ID는 동일 하 게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-215">If you refresh the page every few seconds, the server ID remains the same.</span></span> <span data-ttu-id="4ae98-216">이 문제가 발생 하는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="4ae98-216">Why does this happen?</span></span> <span data-ttu-id="4ae98-217">여기에는 두 가지 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-217">There are two factors at play here.</span></span>

<span data-ttu-id="4ae98-218">먼저 Kubernetes 서비스 검색 시스템은 기본적으로 "라운드 로빈" 부하 분산을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-218">First, the Kubernetes service discovery system uses "round-robin" load-balancing by default.</span></span> <span data-ttu-id="4ae98-219">DNS 서버가 처음으로 쿼리 될 때 서비스에 대해 일치 하는 첫 번째 IP 주소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-219">The first time the DNS server is queried, it will return the first matching IP address for the service.</span></span> <span data-ttu-id="4ae98-220">종료 될 때까지 다음 번에 목록에서 다음 IP 주소를 지정 하는 방식으로 끝까지 반복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-220">The next time, the next IP address in the list, and so on, until the end, at which point it loops back to the start.</span></span>

<span data-ttu-id="4ae98-221">두 번째로 StockWeb 응용 프로그램의 gRPC 클라이언트에 사용 되는 `HttpClient`은 [ASP.NET Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md)에서 만들어지고 관리 되며이 클라이언트의 단일 인스턴스는 페이지에 대 한 모든 호출에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-221">Second, the `HttpClient` used for the StockWeb application's gRPC client is created and managed by the [ASP.NET Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md), and a single instance of this client is used for every call to the page.</span></span> <span data-ttu-id="4ae98-222">클라이언트는 하나의 DNS 조회만 수행 하므로 모든 요청은 동일한 IP 주소로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-222">The client only does one DNS lookup, so all requests are routed to the same IP address.</span></span> <span data-ttu-id="4ae98-223">또한 `HttpClientHandler`는 성능상의 이유로 캐시 되므로 빠른 연속의 여러 요청은 캐시 된 DNS 항목이 만료 되거나 특정 이유로 인해 처리기 인스턴스가 삭제 될 때까지 *모두* 동일한 IP 주소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-223">Furthermore, because the `HttpClientHandler` is cached for performance reasons, multiple requests in quick succession will *all* use the same IP address, until the cached DNS entry expires or the handler instance is disposed for some reason.</span></span>

<span data-ttu-id="4ae98-224">즉, gRPC 서비스에 대 한 요청은 기본적으로 클러스터에 있는 해당 서비스의 모든 인스턴스에 걸쳐 분산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-224">This means that by default requests to a gRPC service aren't balanced across all instances of that service in the cluster.</span></span> <span data-ttu-id="4ae98-225">소비자는 서로 다른 인스턴스를 사용 하지만 요청 및 리소스의 균형 된 사용을 보장 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-225">Different consumers will use different instances, but that doesn't guarantee a good distribution of requests and a balanced use of resources.</span></span>

<span data-ttu-id="4ae98-226">다음 챕터 [서비스인 Service](service-mesh.md)는이 문제를 해결 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ae98-226">The next chapter, [Service Meshes](service-mesh.md), will look at how to address this problem.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4ae98-227">[이전](docker.md)
>[다음](service-mesh.md)</span><span class="sxs-lookup"><span data-stu-id="4ae98-227">[Previous](docker.md)
[Next](service-mesh.md)</span></span>

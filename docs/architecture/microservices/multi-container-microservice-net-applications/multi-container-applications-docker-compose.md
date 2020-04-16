---
title: docker-compose.yml을 사용하여 다중 컨테이너 애플리케이션 정의
description: docker-compose.yml을 사용하여 다중 컨테이너 애플리케이션에서 마이크로 서비스 컴퍼지션을 지정하는 방법입니다.
ms.date: 01/30/2020
ms.openlocfilehash: 029fad8bb912457872dd5817a2f76aed57dc53c6
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888230"
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a><span data-ttu-id="142e7-103">docker-compose.yml을 사용하여 다중 컨테이너 애플리케이션 정의</span><span class="sxs-lookup"><span data-stu-id="142e7-103">Defining your multi-container application with docker-compose.yml</span></span>

<span data-ttu-id="142e7-104">이 가이드에서 [docker compose.yml](https://docs.docker.com/compose/compose-file/) 파일은 섹션 [4단계. 다중 컨테이너 Docker 애플리케이션을 빌드할 때 docker compose.yml 파일에서 서비스 정의](../docker-application-development-process/docker-app-development-workflow.md#step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application)에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-104">In this guide, the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file was introduced in the section [Step 4. Define your services in docker-compose.yml when building a multi-container Docker application](../docker-application-development-process/docker-app-development-workflow.md#step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application).</span></span> <span data-ttu-id="142e7-105">그러나 더 자세히 살펴볼 가치가 있는 docker-compose 파일을 사용하는 다른 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-105">However, there are additional ways to use the docker-compose files that are worth exploring in further detail.</span></span>

<span data-ttu-id="142e7-106">예를 들어 docker-compose.yml 파일에서 다중 컨테이너 애플리케이션을 배포하려는 방법을 명시적으로 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-106">For example, you can explicitly describe how you want to deploy your multi-container application in the docker-compose.yml file.</span></span> <span data-ttu-id="142e7-107">필요에 따라 사용자 지정 Docker 이미지를 작성하려는 방법을 설명할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-107">Optionally, you can also describe how you are going to build your custom Docker images.</span></span> <span data-ttu-id="142e7-108">(사용자 지정 Docker 이미지는 Docker CLI를 사용하여 빌드될 수도 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="142e7-108">(Custom Docker images can also be built with the Docker CLI.)</span></span>

<span data-ttu-id="142e7-109">기본적으로 배포하려는 각 컨테이너와 각 컨테이너 배포에 대한 특정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-109">Basically, you define each of the containers you want to deploy plus certain characteristics for each container deployment.</span></span> <span data-ttu-id="142e7-110">다중 컨테이너 배포 설명 파일을 가지면 [docker-compose up](https://docs.docker.com/compose/overview/) CLI 명령으로 오케스트레이션된 단일 작업에서 전체 솔루션을 배포하거나 Visual Studio에서 투명하게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-110">Once you have a multi-container deployment description file, you can deploy the whole solution in a single action orchestrated by the [docker-compose up](https://docs.docker.com/compose/overview/) CLI command, or you can deploy it transparently from Visual Studio.</span></span> <span data-ttu-id="142e7-111">그렇지 않은 경우 명령 줄에서 `docker run` 명령을 사용하여 여러 단계에서 컨테이너별로 배포하는 Docker CLI를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-111">Otherwise, you would need to use the Docker CLI to deploy container-by-container in multiple steps by using the `docker run` command from the command line.</span></span> <span data-ttu-id="142e7-112">따라서 docker-compose.yml에 정의된 각 서비스는 정확하게 하나의 이미지 또는 빌드를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-112">Therefore, each service defined in docker-compose.yml must specify exactly one image or build.</span></span> <span data-ttu-id="142e7-113">다른 키는 선택 사항이며 `docker run` 명령줄 함수와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-113">Other keys are optional, and are analogous to their `docker run` command-line counterparts.</span></span>

<span data-ttu-id="142e7-114">다음 YAML 코드는 가능한 전역의 정의이며 eShopOnContainers 샘플에 대한 단일 docker-compose.yml 파일이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-114">The following YAML code is the definition of a possible global but single docker-compose.yml file for the eShopOnContainers sample.</span></span> <span data-ttu-id="142e7-115">eShopOnContainers에서 실제 docker-compose 파일이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-115">This is not the actual docker-compose file from eShopOnContainers.</span></span> <span data-ttu-id="142e7-116">대신 단일 파일에서 단순화되고 통합된 버전입니다. 나중에 설명되는 것처럼 docker-compose 파일을 사용하는 가장 좋은 방법이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-116">Instead, it is a simplified and consolidated version in a single file, which is not the best way to work with docker-compose files, as will be explained later.</span></span>

```yml
version: '3.4'

services:
  webmvc:
    image: eshop/webmvc
    environment:
      - CatalogUrl=http://catalog-api
      - OrderingUrl=http://ordering-api
      - BasketUrl=http://basket-api
    ports:
      - "5100:80"
    depends_on:
      - catalog-api
      - ordering-api
      - basket-api

  catalog-api:
    image: eshop/catalog-api
    environment:
      - ConnectionString=Server=sqldata;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata

  ordering-api:
    image: eshop/ordering-api
    environment:
      - ConnectionString=Server=sqldata;Database=Services.OrderingDb;User Id=sa;Password=your@password
    ports:
      - "5102:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata

  basket-api:
    image: eshop/basket-api
    environment:
      - ConnectionString=sqldata
    ports:
      - "5103:80"
    depends_on:
      - sqldata

  sqldata:
    environment:
      - SA_PASSWORD=your@password
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"

  basketdata:
    image: redis
```

<span data-ttu-id="142e7-117">이 파일의 루트 키는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-117">The root key in this file is services.</span></span> <span data-ttu-id="142e7-118">해당 키에서 `docker-compose up` 명령을 실행하거나 이 docker-compose.yml 파일을 사용하여 Visual Studio에서 배포할 때 배포 및 실행하려는 서비스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-118">Under that key, you define the services you want to deploy and run when you execute the `docker-compose up` command or when you deploy from Visual Studio by using this docker-compose.yml file.</span></span> <span data-ttu-id="142e7-119">이 경우 docker-compose.yml 파일에는 다음 표에 설명된 대로 정의된 여러 서비스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-119">In this case, the docker-compose.yml file has multiple services defined, as described in the following table.</span></span>

| <span data-ttu-id="142e7-120">서비스 이름</span><span class="sxs-lookup"><span data-stu-id="142e7-120">Service name</span></span> | <span data-ttu-id="142e7-121">설명</span><span class="sxs-lookup"><span data-stu-id="142e7-121">Description</span></span> |
|--------------|-------------|
| <span data-ttu-id="142e7-122">webmvc</span><span class="sxs-lookup"><span data-stu-id="142e7-122">webmvc</span></span>       | <span data-ttu-id="142e7-123">서버 쪽 C\#에서 마이크로 서비스를 사용하는 ASP.NET Core MVC 애플리케이션을 포함하는 컨테이너</span><span class="sxs-lookup"><span data-stu-id="142e7-123">Container including the ASP.NET Core MVC application consuming the microservices from server-side C\#</span></span>|
| <span data-ttu-id="142e7-124">catalog-api</span><span class="sxs-lookup"><span data-stu-id="142e7-124">catalog-api</span></span>  | <span data-ttu-id="142e7-125">Catalog ASP.NET Core Web API 마이크로 서비스를 포함하는 컨테이너</span><span class="sxs-lookup"><span data-stu-id="142e7-125">Container including the Catalog ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="142e7-126">ordering-api</span><span class="sxs-lookup"><span data-stu-id="142e7-126">ordering-api</span></span> | <span data-ttu-id="142e7-127">Ordering ASP.NET Core Web API 마이크로 서비스를 포함하는 컨테이너</span><span class="sxs-lookup"><span data-stu-id="142e7-127">Container including the Ordering ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="142e7-128">sqldata</span><span class="sxs-lookup"><span data-stu-id="142e7-128">sqldata</span></span>     | <span data-ttu-id="142e7-129">마이크로 서비스 데이터베이스를 보유하는 Linux용 SQL Server를 실행하는 컨테이너</span><span class="sxs-lookup"><span data-stu-id="142e7-129">Container running SQL Server for Linux, holding the microservices databases</span></span> |
| <span data-ttu-id="142e7-130">basket-api</span><span class="sxs-lookup"><span data-stu-id="142e7-130">basket-api</span></span>   | <span data-ttu-id="142e7-131">Basket ASP.NET Core Web API 마이크로 서비스가 있는 컨테이너</span><span class="sxs-lookup"><span data-stu-id="142e7-131">Container with the Basket ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="142e7-132">basketdata</span><span class="sxs-lookup"><span data-stu-id="142e7-132">basketdata</span></span>  | <span data-ttu-id="142e7-133">REDIS 캐시로 바구니 데이터베이스가 있는 REDIS 캐시 서비스를 실행하는 컨테이너</span><span class="sxs-lookup"><span data-stu-id="142e7-133">Container running the REDIS cache service, with the basket database as a REDIS cache</span></span> |

### <a name="a-simple-web-service-api-container"></a><span data-ttu-id="142e7-134">단순한 Web Service API 컨테이너</span><span class="sxs-lookup"><span data-stu-id="142e7-134">A simple Web Service API container</span></span>

<span data-ttu-id="142e7-135">단일 컨테이너에 집중하는 catalog-api 컨테이너 마이크로 서비스에는 간단한 정의가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-135">Focusing on a single container, the catalog-api container-microservice has a straightforward definition:</span></span>

```yml
  catalog-api:
    image: eshop/catalog-api
    environment:
      - ConnectionString=Server=sqldata;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata
```

<span data-ttu-id="142e7-136">이 컨테이너화된 서비스에는 다음과 같은 기본 구성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-136">This containerized service has the following basic configuration:</span></span>

- <span data-ttu-id="142e7-137">사용자 지정 **eshop/catalog-api** 이미지를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-137">It is based on the custom **eshop/catalog-api** image.</span></span> <span data-ttu-id="142e7-138">편의상 파일에 키 설정이라는 빌드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-138">For simplicity's sake, there is no build: key setting in the file.</span></span> <span data-ttu-id="142e7-139">즉, 이미지는 모든 Docker 레지스트리에서 이전에 docker 빌드로 빌드되었거나 docker pull 명령으로 다운로드되었어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-139">This means that the image must have been previously built (with docker build) or have been downloaded (with the docker pull command) from any Docker registry.</span></span>

- <span data-ttu-id="142e7-140">카탈로그 데이터 모델을 포함하는 SQL Server 인스턴스에 액세스하기 위해 Entity Framework에서 사용되는 연결 문자열로 ConnectionString이라는 환경 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-140">It defines an environment variable named ConnectionString with the connection string to be used by Entity Framework to access the SQL Server instance that contains the catalog data model.</span></span> <span data-ttu-id="142e7-141">이 경우 동일한 SQL Server 컨테이너는 여러 데이터베이스를 보유하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-141">In this case, the same SQL Server container is holding multiple databases.</span></span> <span data-ttu-id="142e7-142">따라서 Docker에 대한 개발 컴퓨터에 적은 메모리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-142">Therefore, you need less memory in your development machine for Docker.</span></span> <span data-ttu-id="142e7-143">그러나 각 마이크로 서비스 데이터베이스에 대해 하나의 SQL Server 컨테이너를 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-143">However, you could also deploy one SQL Server container for each microservice database.</span></span>

- <span data-ttu-id="142e7-144">SQL Server 이름은 **sqldata**입니다. 이는 Linux용 SQL Server 인스턴스를 실행하는 컨테이너에 사용되는 동일한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-144">The SQL Server name is **sqldata**, which is the same name used for the container that is running the SQL Server instance for Linux.</span></span> <span data-ttu-id="142e7-145">이 방법은 편리합니다. 이 이름 확인(Docker 호스트에 대한 내부)을 사용할 수 있는 것은 네트워크 주소를 해결하므로 다른 컨테이너에서 액세스하는 컨테이너에 대한 내부 IP를 알지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-145">This is convenient; being able to use this name resolution (internal to the Docker host) will resolve the network address so you don't need to know the internal IP for the containers you are accessing from other containers.</span></span>

<span data-ttu-id="142e7-146">연결 문자열은 환경 변수에 의해 정의되므로 다른 메커니즘을 통해 다른 시간에 해당 변수를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-146">Because the connection string is defined by an environment variable, you could set that variable through a different mechanism and at a different time.</span></span> <span data-ttu-id="142e7-147">예를 들어 최종 호스트에서 프로덕션에 배포할 때 또는 Azure DevOps Services 또는 기본 DevOps 시스템의 CI/CD 파이프라인에서 수행하여 다른 연결 문자열을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-147">For example, you could set a different connection string when deploying to production in the final hosts, or by doing it from your CI/CD pipelines in Azure DevOps Services or your preferred DevOps system.</span></span>

- <span data-ttu-id="142e7-148">Docker 호스트 내에서 **catalog-api** 서비스에 대한 내부 엑세스에 대해 포트 80을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-148">It exposes port 80 for internal access to the **catalog-api** service within the Docker host.</span></span> <span data-ttu-id="142e7-149">호스트는 Linux용 Docker 이미지를 기반으로 하므로 현재 Linux VM이지만 Windows 이미지에서 대신 실행하도록 컨테이너를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-149">The host is currently a Linux VM because it is based on a Docker image for Linux, but you could configure the container to run on a Windows image instead.</span></span>

- <span data-ttu-id="142e7-150">컨테이너의 노출된 포트 80을 Docker 호스트 컴퓨터(Linux VM)의 포트 5101에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-150">It forwards the exposed port 80 on the container to port 5101 on the Docker host machine (the Linux VM).</span></span>

- <span data-ttu-id="142e7-151">웹 서비스를 **sqldata** 서비스(컨테이너에서 실행되는 Linux 데이터베이스에 대한 SQL Server 인스턴스)에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-151">It links the web service to the **sqldata** service (the SQL Server instance for Linux database running in a container).</span></span> <span data-ttu-id="142e7-152">이 종속성을 지정하면 catalog-api 컨테이너는 sqldata 컨테이너가 시작하기 전까지 시작하지 않습니다. catalog-api는 실행 중인 SQL Server 데이터베이스가 먼저 있어야 하기 때문에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-152">When you specify this dependency, the catalog-api container will not start until the sqldata container has already started; this is important because catalog-api needs to have the SQL Server database up and running first.</span></span> <span data-ttu-id="142e7-153">그러나 이러한 종류의 컨테이너 종속성은 Docker가 컨테이너 수준에서만 확인하기 때문에 많은 경우에서 충분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-153">However, this kind of container dependency is not enough in many cases, because Docker checks only at the container level.</span></span> <span data-ttu-id="142e7-154">경우에 따라 서비스(이 경우 SQL Server)는 여전히 준비되지 않을 수 있으므로 클라이언트 마이크로 서비스에서 지수 백오프로 재시도 논리를 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-154">Sometimes the service (in this case SQL Server) might still not be ready, so it is advisable to implement retry logic with exponential backoff in your client microservices.</span></span> <span data-ttu-id="142e7-155">이런 방식으로 종속성 컨테이너가 짧은 시간 동안 준비되지 않는 경우 애플리케이션은 계속해서 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-155">That way, if a dependency container is not ready for a short time, the application will still be resilient.</span></span>

- <span data-ttu-id="142e7-156">외부 서버에 대한 액세스를 허용하도록 구성됩니다. 추가\_호스트 설정을 통해 개발 PC의 로컬 SQL Server 인스턴스와 같은 외부 서버 또는 Docker 호스트 외부의 컴퓨터에 액세스할 수 있습니다(즉, 개발 Docker 호스트인 기본 Linux VM의 외부).</span><span class="sxs-lookup"><span data-stu-id="142e7-156">It is configured to allow access to external servers: the extra\_hosts setting allows you to access external servers or machines outside of the Docker host (that is, outside the default Linux VM, which is a development Docker host), such as a local SQL Server instance on your development PC.</span></span>

<span data-ttu-id="142e7-157">다음 섹션에서 설명하는 다른 고급 `docker-compose.yml` 설정도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-157">There are also other, more advanced `docker-compose.yml` settings that we'll discuss in the following sections.</span></span>

### <a name="using-docker-compose-files-to-target-multiple-environments"></a><span data-ttu-id="142e7-158">여러 환경을 대상으로 하는 docker-compose 파일 사용</span><span class="sxs-lookup"><span data-stu-id="142e7-158">Using docker-compose files to target multiple environments</span></span>

<span data-ttu-id="142e7-159">`docker-compose.*.yml` 파일은 정의 파일이며 해당 형식을 이해하는 여러 인프라에서 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-159">The `docker-compose.*.yml` files are definition files and can be used by multiple infrastructures that understand that format.</span></span> <span data-ttu-id="142e7-160">가장 간단한 도구는 docker-compose 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-160">The most straightforward tool is the docker-compose command.</span></span>

<span data-ttu-id="142e7-161">따라서 docker-compose 명령을 사용하여 다음과 같은 주요 시나리오를 대상으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-161">Therefore, by using the docker-compose command you can target the following main scenarios.</span></span>

#### <a name="development-environments"></a><span data-ttu-id="142e7-162">개발 환경</span><span class="sxs-lookup"><span data-stu-id="142e7-162">Development environments</span></span>

<span data-ttu-id="142e7-163">애플리케이션을 개발하는 경우 격리된 개발 환경에서 애플리케이션을 실행할 수 있어야 하는 것은 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-163">When you develop applications, it is important to be able to run an application in an isolated development environment.</span></span> <span data-ttu-id="142e7-164">docker-compose CLI 명령을 사용하여 해당 환경을 만들거나 내부에서 docker-compose를 사용하는 Visual Studio를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-164">You can use the docker-compose CLI command to create that environment or Visual Studio, which uses docker-compose under the covers.</span></span>

<span data-ttu-id="142e7-165">docker-compose.yml 파일을 사용하면 모든 애플리케이션의 서비스 종속성(다른 서비스, 캐시, 데이터베이스, 큐 등)을 구성하고 문서화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-165">The docker-compose.yml file allows you to configure and document all your application's service dependencies (other services, cache, databases, queues, etc.).</span></span> <span data-ttu-id="142e7-166">docker-compose CLI 명령을 사용하여 단일 명령(docker-compose up)으로 각 종속성에 대해 하나 이상의 컨테이너를 만들고 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-166">Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).</span></span>

<span data-ttu-id="142e7-167">docker-compose.yml 파일은 Docker 엔진으로 해석되는 구성 파일이지만 다중 컨테이너 애플리케이션의 구성에 대한 편리한 문서 파일의 역할도 합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-167">The docker-compose.yml files are configuration files interpreted by Docker engine but also serve as convenient documentation files about the composition of your multi-container application.</span></span>

#### <a name="testing-environments"></a><span data-ttu-id="142e7-168">테스트 환경</span><span class="sxs-lookup"><span data-stu-id="142e7-168">Testing environments</span></span>

<span data-ttu-id="142e7-169">모든 CD(지속적인 배포) 또는 CI(지속적인 통합) 프로세스의 중요한 부분은 단위 테스트 및 통합 테스트입니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-169">An important part of any continuous deployment (CD) or continuous integration (CI) process are the unit tests and integration tests.</span></span> <span data-ttu-id="142e7-170">이 자동화된 테스트는 격리된 환경이 필요하므로 사용자 또는 애플리케이션 데이터의 다른 변경 내용에 의해 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-170">These automated tests require an isolated environment so they are not impacted by the users or any other change in the application's data.</span></span>

<span data-ttu-id="142e7-171">Docker Compose를 사용하여 다음 명령과 같이 명령 프롬프트 또는 스크립트의 몇 가지 명령에서 매우 쉽게 격리된 해당 환경을 만들고 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-171">With Docker Compose, you can create and destroy that isolated environment very easily in a few commands from your command prompt or scripts, like the following commands:</span></span>

```console
docker-compose -f docker-compose.yml -f docker-compose-test.override.yml up -d
./run_unit_tests
docker-compose -f docker-compose.yml -f docker-compose-test.override.yml down
```

#### <a name="production-deployments"></a><span data-ttu-id="142e7-172">프로덕션 배포</span><span class="sxs-lookup"><span data-stu-id="142e7-172">Production deployments</span></span>

<span data-ttu-id="142e7-173">Compose를 사용하여 원격 Docker 엔진에 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-173">You can also use Compose to deploy to a remote Docker Engine.</span></span> <span data-ttu-id="142e7-174">일반적인 경우는 단일 Docker 호스트 인스턴스를 배포하는 것입니다(예: 프로덕션 VM 또는 [Docker 컴퓨터](https://docs.docker.com/machine/overview/)로 프로비전된 서버).</span><span class="sxs-lookup"><span data-stu-id="142e7-174">A typical case is to deploy to a single Docker host instance (like a production VM or server provisioned with [Docker Machine](https://docs.docker.com/machine/overview/)).</span></span>

<span data-ttu-id="142e7-175">다른 오케스트레이터(Azure Service Fabric, Kubernetes 등)를 사용하는 경우 다른 오케스트레이터에서 필요한 형식이 아닌 docker-compose.yml의 형식과 같은 설정 및 메타데이터 구성 설정을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-175">If you are using any other orchestrator (Azure Service Fabric, Kubernetes, etc.), you might need to add setup and metadata configuration settings like those in docker-compose.yml, but in the format required by the other orchestrator.</span></span>

<span data-ttu-id="142e7-176">어떤 경우에서든 docker-compose는 프로덕션 워크플로가 사용하는 오케스트레이터에 따라 다를 수 있음에도 불구하고 개발, 테스트 및 프로덕션 워크플로에 편리한 도구 및 메타데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-176">In any case, docker-compose is a convenient tool and metadata format for development, testing and production workflows, although the production workflow might vary on the orchestrator you are using.</span></span>

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a><span data-ttu-id="142e7-177">여러 환경을 처리하는 데 다중 docker-compose 파일 사용</span><span class="sxs-lookup"><span data-stu-id="142e7-177">Using multiple docker-compose files to handle several environments</span></span>

<span data-ttu-id="142e7-178">다양한 환경을 대상으로 하는 경우 다중 compose 파일을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-178">When targeting different environments, you should use multiple compose files.</span></span> <span data-ttu-id="142e7-179">이를 통해 환경에 따라 여러 구성 변형을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-179">This lets you create multiple configuration variants depending on the environment.</span></span>

#### <a name="overriding-the-base-docker-compose-file"></a><span data-ttu-id="142e7-180">기본 docker-compose 파일 재정의</span><span class="sxs-lookup"><span data-stu-id="142e7-180">Overriding the base docker-compose file</span></span>

<span data-ttu-id="142e7-181">이전 섹션에 표시된 간소화된 예제에서와 같이 단일 docker-compose.yml 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-181">You could use a single docker-compose.yml file as in the simplified examples shown in previous sections.</span></span> <span data-ttu-id="142e7-182">그러나 대부분의 애플리케이션에 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-182">However, that is not recommended for most applications.</span></span>

<span data-ttu-id="142e7-183">기본적으로 Compose는 두 개의 파일, docker-compose.yml 및 선택적 docker-compose.override.yml 파일을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-183">By default, Compose reads two files, a docker-compose.yml and an optional docker-compose.override.yml file.</span></span> <span data-ttu-id="142e7-184">그림 6-11과 같이 Visual Studio를 사용하고 Docker 지원을 활성화 하도록 설정하여, Visual Studio도 애플리케이션의 디버깅을 위한 추가 docker-compose.vs.debug.g.yml 파일을 만듭니다. 기본 솔루션 폴더에서 obj\\Docker\\ 폴더에서 이 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-184">As shown in Figure 6-11, when you are using Visual Studio and enabling Docker support, Visual Studio also creates an additional docker-compose.vs.debug.g.yml file for debugging the application, you can take a look at this file in folder obj\\Docker\\ in the main solution folder.</span></span>

![Docker Compose 프로젝트의 파일.](./media/multi-container-applications-docker-compose/docker-compose-file-visual-studio.png)

<span data-ttu-id="142e7-186">**그림 6-11**.</span><span class="sxs-lookup"><span data-stu-id="142e7-186">**Figure 6-11**.</span></span> <span data-ttu-id="142e7-187">Visual Studio 2019의 docker-compose 파일</span><span class="sxs-lookup"><span data-stu-id="142e7-187">docker-compose files in Visual Studio 2019</span></span>

<span data-ttu-id="142e7-188">**Docker Compose** 프로젝트 파일 구조:</span><span class="sxs-lookup"><span data-stu-id="142e7-188">**docker-compose** project file structure:</span></span>

- <span data-ttu-id="142e7-189">*.dockerignore* - 파일을 무시하는 데 사용</span><span class="sxs-lookup"><span data-stu-id="142e7-189">*.dockerignore* - used to ignore files</span></span>
- <span data-ttu-id="142e7-190">*docker-compose.yml* - 마이크로 서비스를 작성하는 데 사용</span><span class="sxs-lookup"><span data-stu-id="142e7-190">*docker-compose.yml* - used to compose microservices</span></span>
- <span data-ttu-id="142e7-191">*docker-compose.override.yml* - 마이크로 서비스 환경을 구성하는 데 사용</span><span class="sxs-lookup"><span data-stu-id="142e7-191">*docker-compose.override.yml* - used to configure microservices environment</span></span>

<span data-ttu-id="142e7-192">Visual Studio Code 또는 Sublime과 같은 편집기를 사용하여 docker-compose 파일을 편집하고 docker-compose up 명령을 사용하여 애플리케이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-192">You can edit the docker-compose files with any editor, like Visual Studio Code or Sublime, and run the application with the docker-compose up command.</span></span>

<span data-ttu-id="142e7-193">규칙에 따라 docker-compose.yml 파일은 기본 구성 및 기타 정적 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-193">By convention, the docker-compose.yml file contains your base configuration and other static settings.</span></span> <span data-ttu-id="142e7-194">즉, 서비스 구성은 대상으로 하는 배포 환경에 따라 변경되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-194">That means that the service configuration should not change depending on the deployment environment you are targeting.</span></span>

<span data-ttu-id="142e7-195">해당 이름에서 알 수 있듯이 docker-compose.override.yml 파일은 배포 환경에 따라 달라지는 구성과 같은 기본 구성을 재정의하는 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-195">The docker-compose.override.yml file, as its name suggests, contains configuration settings that override the base configuration, such as configuration that depends on the deployment environment.</span></span> <span data-ttu-id="142e7-196">또한 서로 다른 이름을 가진 여러 재정의 파일을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-196">You can have multiple override files with different names also.</span></span> <span data-ttu-id="142e7-197">재정의 파일은 일반적으로 환경 또는 배포에 관련된 애플리케이션에 필요한 추가 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-197">The override files usually contain additional information needed by the application but specific to an environment or to a deployment.</span></span>

#### <a name="targeting-multiple-environments"></a><span data-ttu-id="142e7-198">여러 환경을 대상으로 지정</span><span class="sxs-lookup"><span data-stu-id="142e7-198">Targeting multiple environments</span></span>

<span data-ttu-id="142e7-199">일반적인 사용 사례는 프로덕션, 준비, CI 또는 개발과 같은 여러 환경을 대상으로 지정할 수 있도록 여러 compose 파일을 정의하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-199">A typical use case is when you define multiple compose files so you can target multiple environments, like production, staging, CI, or development.</span></span> <span data-ttu-id="142e7-200">이러한 차이를 지원하기 위해 그림 6-12에 나와 있는 것처럼 Compose 구성을 여러 파일로 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-200">To support these differences, you can split your Compose configuration into multiple files, as shown in Figure 6-12.</span></span>

![기본 파일을 재정의하도록 설정된 세 가지 docker-compose 파일의 다이어그램](./media/multi-container-applications-docker-compose/multiple-docker-compose-files-override-base.png)

<span data-ttu-id="142e7-202">**그림 6-12**.</span><span class="sxs-lookup"><span data-stu-id="142e7-202">**Figure 6-12**.</span></span> <span data-ttu-id="142e7-203">기본 docker-compose.yml 파일에서 값을 재정의하는 다중 docker-compose 파일</span><span class="sxs-lookup"><span data-stu-id="142e7-203">Multiple docker-compose files overriding values in the base docker-compose.yml file</span></span>

<span data-ttu-id="142e7-204">여러 docker-compose\*.yml 파일을 결합하여 다른 환경을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-204">You can combine multiple docker-compose\*.yml files to handle different environments.</span></span> <span data-ttu-id="142e7-205">기본 docker-compose.yml 파일로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-205">You start with the base docker-compose.yml file.</span></span> <span data-ttu-id="142e7-206">이 기본 파일은 환경에 따라 변경되지 않는 기본 또는 정적 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-206">This base file contains the base or static configuration settings that do not change depending on the environment.</span></span> <span data-ttu-id="142e7-207">예를 들어 eShopOnContainers 앱에는 기본 파일로 다음과 같은 docker-compose.yml(더 적은 서비스로 단순화된) 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-207">For example, the eShopOnContainers app has the following docker-compose.yml file (simplified with fewer services) as the base file.</span></span>

```yml
#docker-compose.yml (Base)
version: '3.4'
services:
  basket-api:
    image: eshop/basket-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Basket/Basket.API/Dockerfile
    depends_on:
      - basketdata
      - identity-api
      - rabbitmq

  catalog-api:
    image: eshop/catalog-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Catalog/Catalog.API/Dockerfile
    depends_on:
      - sqldata
      - rabbitmq

  marketing-api:
    image: eshop/marketing-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Marketing/Marketing.API/Dockerfile
    depends_on:
      - sqldata
      - nosqldata
      - identity-api
      - rabbitmq

  webmvc:
    image: eshop/webmvc:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Web/WebMVC/Dockerfile
    depends_on:
      - catalog-api
      - ordering-api
      - identity-api
      - basket-api
      - marketing-api

  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest

  nosqldata:
    image: mongo

  basketdata:
    image: redis

  rabbitmq:
    image: rabbitmq:3-management

```

<span data-ttu-id="142e7-208">다른 대상 배포 환경으로 인해 기본 docker-compose.yml 파일의 값을 변경하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="142e7-208">The values in the base docker-compose.yml file should not change because of different target deployment environments.</span></span>

<span data-ttu-id="142e7-209">예를 들어 webmvc 서비스 정의에 집중하는 경우 대상으로 할 수 있는 환경에 관계 없이 해당 정보가 동일한 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-209">If you focus on the webmvc service definition, for instance, you can see how that information is much the same no matter what environment you might be targeting.</span></span> <span data-ttu-id="142e7-210">다음 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-210">You have the following information:</span></span>

- <span data-ttu-id="142e7-211">서비스 이름: webmvc</span><span class="sxs-lookup"><span data-stu-id="142e7-211">The service name: webmvc.</span></span>

- <span data-ttu-id="142e7-212">컨테이너의 사용자 지정 이미지: eshop/webmvc</span><span class="sxs-lookup"><span data-stu-id="142e7-212">The container's custom image: eshop/webmvc.</span></span>

- <span data-ttu-id="142e7-213">사용할 Dockerfile을 나타내는 사용자 지정 Docker 이미지를 빌드하는 명령</span><span class="sxs-lookup"><span data-stu-id="142e7-213">The command to build the custom Docker image, indicating which Dockerfile to use.</span></span>

- <span data-ttu-id="142e7-214">다른 서비스에 대한 종속성, 따라서 이 컨테이너는 다른 종속성 컨테이너가 시작될 때까지 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-214">Dependencies on other services, so this container does not start until the other dependency containers have started.</span></span>

<span data-ttu-id="142e7-215">추가 구성을 가질 수 있지만 중요한 점은 기본 docker-compose.yml 파일에서 환경에 공통되는 정보를 설정하려 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-215">You can have additional configuration, but the important point is that in the base docker-compose.yml file, you just want to set the information that is common across environments.</span></span> <span data-ttu-id="142e7-216">그런 다음, docker-compose.override.yml 또는 프로덕션 또는 스테이징에 대한 유사한 파일에서 각 환경에 관련된 구성을 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-216">Then in the docker-compose.override.yml or similar files for production or staging, you should place configuration that is specific for each environment.</span></span>

<span data-ttu-id="142e7-217">일반적으로 docker-compose.override.yml은 eShopOnContainers의 다음 예제에서와 같이 개발 환경에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-217">Usually, the docker-compose.override.yml is used for your development environment, as in the following example from eShopOnContainers:</span></span>

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '3.4'

services:
# Simplified number of services here:

  basket-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_REDIS_BASKET_DB:-basketdata}
      - identityUrl=http://identity-api
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}
      - AzureServiceBusEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}

    ports:
      - "5103:80"

  catalog-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_CATALOG_DB:-Server=sqldata;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_CATALOG_URL:-http://localhost:5202/api/v1/catalog/items/[0]/pic/}
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_CATALOG_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_CATALOG_KEY}
      - UseCustomizationData=True
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
    ports:
      - "5101:80"

  marketing-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_MARKETING_DB:-Server=sqldata;Database=Microsoft.eShopOnContainers.Services.MarketingDb;User Id=sa;Password=Pass@word}
      - MongoConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosqldata}
      - MongoDatabase=MarketingDb
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}
      - identityUrl=http://identity-api
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - CampaignDetailFunctionUri=${ESHOP_AZUREFUNC_CAMPAIGN_DETAILS_URI}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_MARKETING_URL:-http://localhost:5110/api/v1/campaigns/[0]/pic/}
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_MARKETING_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_MARKETING_KEY}
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5110:80"

  webmvc:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - PurchaseUrl=http://webshoppingapigw
      - IdentityUrl=http://10.0.75.1:5105
      - MarketingUrl=http://webmarketingapigw
      - CatalogUrlHC=http://catalog-api/hc
      - OrderingUrlHC=http://ordering-api/hc
      - IdentityUrlHC=http://identity-api/hc
      - BasketUrlHC=http://basket-api/hc
      - MarketingUrlHC=http://marketing-api/hc
      - PaymentUrlHC=http://payment-api/hc
      - SignalrHubUrl=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5202
      - UseCustomizationData=True
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5100:80"
  sqldata:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
  nosqldata:
    ports:
      - "27017:27017"
  basketdata:
    ports:
      - "6379:6379"
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"

```

<span data-ttu-id="142e7-218">이 예제에서 개발 재정의 구성은 일부 포트를 호스트에 노출하고, 리디렉션 URL로 환경 변수를 정의하고, 개발 환경에 대한 연결 문자열을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-218">In this example, the development override configuration exposes some ports to the host, defines environment variables with redirect URLs, and specifies connection strings for the development environment.</span></span> <span data-ttu-id="142e7-219">이러한 설정은 모두 개발 환경을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-219">These settings are all just for the development environment.</span></span>

<span data-ttu-id="142e7-220">`docker-compose up`을 실행하는 경우(또는 Visual Studio에서 시작) 명령은 두 파일을 병합하는 것처럼 재정의를 자동으로 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-220">When you run `docker-compose up` (or launch it from Visual Studio), the command reads the overrides automatically as if it were merging both files.</span></span>

<span data-ttu-id="142e7-221">프로덕션 환경에 대해 다른 구성 값, 포트 또는 연결 문자열이 있는 다른 Compose 파일을 원한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-221">Suppose that you want another Compose file for the production environment, with different configuration values, ports, or connection strings.</span></span> <span data-ttu-id="142e7-222">다른 설정 및 환경 변수가 있는 `docker-compose.prod.yml`이라는 파일과 같은 다른 재정의 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-222">You can create another override file, like file named `docker-compose.prod.yml` with different settings and environment variables.</span></span> <span data-ttu-id="142e7-223">해당 파일은 다른 Git 리포지토리에 저장되거나 다른 팀에 의해 관리 및 보호될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-223">That file might be stored in a different Git repo or managed and secured by a different team.</span></span>

#### <a name="how-to-deploy-with-a-specific-override-file"></a><span data-ttu-id="142e7-224">특정 재정의 파일로 배포하는 방법</span><span class="sxs-lookup"><span data-stu-id="142e7-224">How to deploy with a specific override file</span></span>

<span data-ttu-id="142e7-225">여러 재정의 파일 또는 다른 이름이 있는 재정의 파일을 사용하려면 docker-compose 명령과 함께 -f 옵션을 사용하고 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-225">To use multiple override files, or an override file with a different name, you can use the -f option with the docker-compose command and specify the files.</span></span> <span data-ttu-id="142e7-226">Compose는 명령줄에 지정된 순서로 파일을 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-226">Compose merges files in the order they are specified on the command line.</span></span> <span data-ttu-id="142e7-227">다음 예제에서는 재정의 파일로 배포하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-227">The following example shows how to deploy with override files.</span></span>

```console
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a><span data-ttu-id="142e7-228">docker-compose 파일에서 환경 변수 사용</span><span class="sxs-lookup"><span data-stu-id="142e7-228">Using environment variables in docker-compose files</span></span>

<span data-ttu-id="142e7-229">이전 예제에서 본 것처럼 환경 변수에서 구성 정보를 얻을 수 있는 것은 특히 프로덕션 환경에서 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-229">It is convenient, especially in production environments, to be able to get configuration information from environment variables, as we have shown in previous examples.</span></span> <span data-ttu-id="142e7-230">구문 ${MY\_VAR}을 사용하여 docker-compose 파일에서 환경 변수를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-230">You can reference an environment variable in your docker-compose files using the syntax ${MY\_VAR}.</span></span> <span data-ttu-id="142e7-231">docker-compose.prod.yml 파일에서 다음 줄은 환경 변수의 값을 참조하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-231">The following line from a docker-compose.prod.yml file shows how to reference the value of an environment variable.</span></span>

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

<span data-ttu-id="142e7-232">환경 변수는 호스트 환경(Linux, Windows, 클라우드 클러스터 등)에 따라 다양한 방법으로 생성 및 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-232">Environment variables are created and initialized in different ways, depending on your host environment (Linux, Windows, Cloud cluster, etc.).</span></span> <span data-ttu-id="142e7-233">그러나 편리한 방법은 .env 파일을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-233">However, a convenient approach is to use an .env file.</span></span> <span data-ttu-id="142e7-234">docker-compose 파일은 .env 파일의 기본 환경 변수 선언을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-234">The docker-compose files support declaring default environment variables in the .env file.</span></span> <span data-ttu-id="142e7-235">환경 변수에 대한 이러한 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-235">These values for the environment variables are the default values.</span></span> <span data-ttu-id="142e7-236">그러나 각 환경(호스트 OS 또는 클러스터의 환경 변수)에서 정의했을 수 있는 값으로 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-236">But they can be overridden by the values you might have defined in each of your environments (host OS or environment variables from your cluster).</span></span> <span data-ttu-id="142e7-237">이 .env 파일을 docker-compose 명령이 실행되는 폴더에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-237">You place this .env file in the folder where the docker-compose command is executed from.</span></span>

<span data-ttu-id="142e7-238">다음 예제에서는 eShopOnContainers 애플리케이션에 대한 [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) 파일과 같은 .env 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-238">The following example shows an .env file like the [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file for the eShopOnContainers application.</span></span>

```sh
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

<span data-ttu-id="142e7-239">docker-compose는 .env 파일의 각 줄이 \<변수\>=\<값\> 형식이 되도록 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-239">Docker-compose expects each line in an .env file to be in the format \<variable\>=\<value\>.</span></span>

<span data-ttu-id="142e7-240">런타임 환경에서 설정된 값은 항상 .env 파일 내부에 정의된 값을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-240">The values set in the run-time environment always override the values defined inside the .env file.</span></span> <span data-ttu-id="142e7-241">비슷한 방식으로 명령줄 인수를 통해 전달된 값도 .env 파일에 설정된 기본값을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-241">In a similar way, values passed via command-line arguments also override the default values set in the .env file.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="142e7-242">추가 자료</span><span class="sxs-lookup"><span data-stu-id="142e7-242">Additional resources</span></span>

- <span data-ttu-id="142e7-243">**Docker Compose 개요** </span><span class="sxs-lookup"><span data-stu-id="142e7-243">**Overview of Docker Compose** </span></span>\
    <https://docs.docker.com/compose/overview/>

- <span data-ttu-id="142e7-244">**다중 계산 파일** </span><span class="sxs-lookup"><span data-stu-id="142e7-244">**Multiple Compose files** </span></span>\
    [https://docs.docker.com/compose/extends/\#multiple-compose-files](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a><span data-ttu-id="142e7-245">최적화된 ASP.NET Core Docker 이미지 빌드</span><span class="sxs-lookup"><span data-stu-id="142e7-245">Building optimized ASP.NET Core Docker images</span></span>

<span data-ttu-id="142e7-246">인터넷에서 원본의 Docker 및 .NET Core를 탐색하는 경우 원본을 컨테이너에 복사하여 Docker 이미지를 빌드하는 것의 용이함을 보여 주는 Dockerfile을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-246">If you are exploring Docker and .NET Core on sources on the Internet, you will find Dockerfiles that demonstrate the simplicity of building a Docker image by copying your source into a container.</span></span> <span data-ttu-id="142e7-247">이러한 예제는 간단한 구성을 사용하는 것을 제안합니다. 애플리케이션과 함께 제공되는 환경으로 Docker 이미지를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-247">These examples suggest that by using a simple configuration, you can have a Docker image with the environment packaged with your application.</span></span> <span data-ttu-id="142e7-248">다음 예제에서는 이 맥락에서 간단한 Dockerfile을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-248">The following example shows a simple Dockerfile in this vein.</span></span>

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/sdk:3.1
WORKDIR /app
ENV ASPNETCORE_URLS http://+:80
EXPOSE 80
COPY . .
RUN dotnet restore
ENTRYPOINT ["dotnet", "run"]
```

<span data-ttu-id="142e7-249">이와 같은 Dockerfile은 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-249">A Dockerfile like this will work.</span></span> <span data-ttu-id="142e7-250">그러나 실질적으로 이미지, 특히 프로덕션 이미지를 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-250">However, you can substantially optimize your images, especially your production images.</span></span>

<span data-ttu-id="142e7-251">컨테이너 및 마이크로 서비스 모델에서 컨테이너를 지속적으로 시작하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-251">In the container and microservices model, you are constantly starting containers.</span></span> <span data-ttu-id="142e7-252">컨테이너를 사용하는 일반적인 방법은 컨테이너가 삭제 가능하므로 중지 중인 컨테이너를 다시 시작하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-252">The typical way of using containers does not restart a sleeping container, because the container is disposable.</span></span> <span data-ttu-id="142e7-253">오케스트레이터(예: Kubernetes 및 Azure Service Fabric)는 단순히 이미지의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-253">Orchestrators (like Kubernetes and Azure Service Fabric) simply create new instances of images.</span></span> <span data-ttu-id="142e7-254">즉, 인스턴스화 프로세스의 속도가 더 빨라지도록 빌드될 때 애플리케이션을 미리 컴파일하여 최적화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-254">What this means is that you would need to optimize by precompiling the application when it is built so the instantiation process will be faster.</span></span> <span data-ttu-id="142e7-255">컨테이너가 시작될 때 실행할 준비가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-255">When the container is started, it should be ready to run.</span></span> <span data-ttu-id="142e7-256">.NET Core 및 Docker에 대한 블로그 게시물에서 볼 수 있는 것처럼 `dotnet restore` 및 `dotnet build` CLI 명령을 사용하여 런타임에 복원 및 컴파일하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="142e7-256">Don't restore and compile at run time using the `dotnet restore` and `dotnet build` CLI commands as you may see in blog posts about .NET Core and Docker.</span></span>

<span data-ttu-id="142e7-257">.NET 팀은 .NET Core 및 ASP.NET Core를 컨테이너 최적화된 프레임워크로 만들도록 중요한 작업을 수행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-257">The .NET team has been doing important work to make .NET Core and ASP.NET Core a container-optimized framework.</span></span> <span data-ttu-id="142e7-258">.NET Core는 작은 메모리 공간을 가진 경량 프레임워크일 뿐만 아니라, 팀은 세 가지 주요 시나리오에 최적화된 Docker 이미지를 중점적으로 사용해 *dotnet/core*에서 버전 2.1부터 Docker 허브 레지스트리에 게시했습니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-258">Not only is .NET Core a lightweight framework with a small memory footprint; the team has focused on optimized Docker images for three main scenarios and published them in the Docker Hub registry at *dotnet/core*, beginning with version 2.1:</span></span>

1. <span data-ttu-id="142e7-259">**개발**: 우선 순위는 변경 내용을 신속하게 반복하고 디버그할 수 있는 기능이며, 크기는 부차적 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-259">**Development**: The priority is the ability to quickly iterate and debug changes, and where size is secondary.</span></span>

2. <span data-ttu-id="142e7-260">**빌드:** 우선 순위는 애플리케이션을 컴파일하는 것이며 이미지는 이진 파일을 최적화하기 위해 이진 파일 및 다른 종속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-260">**Build**: The priority is compiling the application, and the image includes binaries and other dependencies to optimize binaries.</span></span>

3. <span data-ttu-id="142e7-261">**프로덕션**: 컨테이너의 빠른 배포 및 시작이 포커스인 경우, 이 이미지는 이진 파일 및 애플리케이션을 실행할 콘텐츠로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-261">**Production**: The focus is fast deploying and starting of containers, so these images are limited to the binaries and content needed to run the application.</span></span>

<span data-ttu-id="142e7-262">.NET 팀은 [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/)(Docker Hub)에서 네 가지 기본 변형을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-262">The .NET team provides four basic variants in [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) (at Docker Hub):</span></span>

1. <span data-ttu-id="142e7-263">**sdk**: 개발 및 빌드 시나리오용</span><span class="sxs-lookup"><span data-stu-id="142e7-263">**sdk**: for development and build scenarios</span></span>
1. <span data-ttu-id="142e7-264">**aspnet**: ASP.NET 프로덕션 시나리오용</span><span class="sxs-lookup"><span data-stu-id="142e7-264">**aspnet**: for ASP.NET production scenarios</span></span>
1. <span data-ttu-id="142e7-265">**runtime**: .NET 프로덕션 시나리오용</span><span class="sxs-lookup"><span data-stu-id="142e7-265">**runtime**: for .NET production scenarios</span></span>
1. <span data-ttu-id="142e7-266">**runtime-deps**: [자체 포함된 애플리케이션](../../../core/deploying/index.md#publish-self-contained)의 프로덕션 시나리오용.</span><span class="sxs-lookup"><span data-stu-id="142e7-266">**runtime-deps**: for production scenarios of [self-contained applications](../../../core/deploying/index.md#publish-self-contained)</span></span>

<span data-ttu-id="142e7-267">빠른 시작을 위해 런타임 이미지도 자동으로 aspnetcore\_urls를 포트 80으로 설정하고 Ngen을 사용하여 어셈블리의 네이티브 이미지 캐시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="142e7-267">For faster startup, runtime images also automatically set aspnetcore\_urls to port 80 and use Ngen to create a native image cache of assemblies.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="142e7-268">추가 자료</span><span class="sxs-lookup"><span data-stu-id="142e7-268">Additional resources</span></span>

- <span data-ttu-id="142e7-269">**ASP.NET Core를 사용하여 최적화된 Docker 이미지 빌드**</span><span class="sxs-lookup"><span data-stu-id="142e7-269">**Building Optimized Docker Images with ASP.NET Core**</span></span>  
  <https://docs.microsoft.com/archive/blogs/stevelasker/building-optimized-docker-images-with-asp-net-core>

- <span data-ttu-id="142e7-270">**.NET Core 애플리케이션에 대한 Docker 이미지 작성**</span><span class="sxs-lookup"><span data-stu-id="142e7-270">**Building Docker Images for .NET Core Applications**</span></span>  
  [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](/aspnet/core/host-and-deploy/docker/building-net-docker-images)

> [!div class="step-by-step"]
> <span data-ttu-id="142e7-271">[이전](data-driven-crud-microservice.md)
> [다음](database-server-container.md)</span><span class="sxs-lookup"><span data-stu-id="142e7-271">[Previous](data-driven-crud-microservice.md)
[Next](database-server-container.md)</span></span>

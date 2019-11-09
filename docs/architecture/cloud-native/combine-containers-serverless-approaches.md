---
title: 컨테이너 및 서버리스 접근 방식 결합
description: 서버를 사용 하지 않는 방법으로 컨테이너와 Kubernetes 결합
ms.date: 06/30/2019
ms.openlocfilehash: 58aff43adbdd2e629370cc685f32c7b61c25f85e
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840594"
---
# <a name="combining-containers-and-serverless-approaches"></a><span data-ttu-id="647f8-103">컨테이너 및 서버리스 접근 방식 결합</span><span class="sxs-lookup"><span data-stu-id="647f8-103">Combining containers and serverless approaches</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="647f8-104">주로 마이크로 서비스 기반 응용 프로그램은 노드 간 통신을 위해 컨테이너, 오케스트레이션 및 메시지 전달에 크게 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-104">Frequently, microservices-based applications rely heavily on containers, orchestration, and message-passing for communication between nodes.</span></span> <span data-ttu-id="647f8-105">이 메시징은 Azure Functions에 이상적인 작업 이지만 응용 프로그램의 나머지 부분을 Kubernetes 및 관련 도구를 사용 하 여 구성 하 고 배포한 후에는이 동일한 도구 집합 내에서 Azure Functions를 활용할 수 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-105">This messaging is an ideal task for Azure Functions, but with the rest of the application configured and deployed using Kubernetes and related tools, it would be nice to be able to leverage Azure Functions within this same toolset.</span></span> <span data-ttu-id="647f8-106">다행히 Kubernetes 기반 앱의 나머지와 동일한 프로세스와 도구를 사용 하 여 Docker 컨테이너에 Azure Functions을 래핑하고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-106">Fortunately, you can wrap Azure Functions in Docker containers and deploy them using the same processes and tools as the rest of your Kubernetes-based app.</span></span>

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a><span data-ttu-id="647f8-107">서버를 사용 하지 않는 컨테이너를 사용 하는 경우는 언제 인가요?</span><span class="sxs-lookup"><span data-stu-id="647f8-107">When does it make sense to use containers with serverless?</span></span>

<span data-ttu-id="647f8-108">기본적으로 서버를 사용 하지 않는 함수는 실행 되는 플랫폼에 대해 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-108">By default, your serverless functions have no knowledge of the platform on which they'll run.</span></span> <span data-ttu-id="647f8-109">그러나 경우에 따라 코드를 실행할 컨테이너 이미지를 사용자 지정 하는 것이 중요 한 특정 요구 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-109">However, in some cases you may have specific requirements that make it important for you to customize the container image in which your code will run.</span></span> <span data-ttu-id="647f8-110">함수가 특정 언어 버전을 사용 하거나 기본 이미지에서 지원 하지 않는 종속성 또는 구성 요구 사항이 있으므로 사용자 지정 이미지를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-110">You may want to use a custom image because your function relies on a specific language version or has dependencies or configuration requirements that aren't supported by the default image.</span></span> <span data-ttu-id="647f8-111">이러한 경우 사용자 고유의 컨테이너를 사용자 지정 하 고 사용자 지정 Docker 컨테이너에 함수를 배포 하는 것이 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-111">In these cases, it may make sense to customize your own container and deploy your function in a custom Docker container.</span></span>

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a><span data-ttu-id="647f8-112">Azure Functions 컨테이너를 사용 하지 않는 경우는 언제 인가요?</span><span class="sxs-lookup"><span data-stu-id="647f8-112">When should you avoid using containers with Azure Functions?</span></span>

<span data-ttu-id="647f8-113">사용자 고유의 컨테이너를 사용 하는 경우 함수에 대 한 소비 계획 청구를 활용 하는 것이 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-113">If you're expecting to benefit from the consumption plan billing for your function, you won't be able to do so if you're using your own container.</span></span> <span data-ttu-id="647f8-114">또한 Docker 컨테이너를 사용 하는 것 외에 함수를 고유한 Kubernetes 클러스터에 배포 하는 경우에는 Azure Functions에서 제공 하는 기본 제공 크기 조정을 더 이상 활용 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-114">What's more, if you go beyond just using a Docker container and deploy your functions to your own Kubernetes cluster, you'll no longer benefit from the built-in scaling provided by Azure Functions.</span></span> <span data-ttu-id="647f8-115">아래에 설명 된 Kubernetes ' 크기 조정 기능을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-115">You'll need to use Kubernetes' scaling features, described below.</span></span>

## <a name="how-to-combine-serverless-and-docker-containers"></a><span data-ttu-id="647f8-116">서버 리스 및 Docker 컨테이너를 결합 하는 방법</span><span class="sxs-lookup"><span data-stu-id="647f8-116">How to combine serverless and Docker containers</span></span>

<span data-ttu-id="647f8-117">Docker 컨테이너에서 Azure 함수를 래핑하려면 Azure Functions Core Tools를 설치한 후 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-117">To wrap an Azure Function in a Docker container, install the Azure Functions Core Tools and then run the following command:</span></span>

```console
func init ProjectName --docker
```

<span data-ttu-id="647f8-118">다음 옵션 중에서 원하는 작업자 런타임을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-118">Choose which worker runtime you want from the following options:</span></span>

- <span data-ttu-id="647f8-119">`dotnet`(C#)</span><span class="sxs-lookup"><span data-stu-id="647f8-119">`dotnet` (C#)</span></span>
- <span data-ttu-id="647f8-120">`node`(JavaScript)</span><span class="sxs-lookup"><span data-stu-id="647f8-120">`node` (JavaScript)</span></span>
- `python`

<span data-ttu-id="647f8-121">프로젝트를 만들 때 Dockerfile이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-121">When the project is created, it will include a Dockerfile.</span></span> <span data-ttu-id="647f8-122">이제 함수를 로컬에서 만들고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-122">Now, you can create and test your function locally.</span></span> <span data-ttu-id="647f8-123">`docker build` 및 `docker run` 명령을 사용 하 여 빌드하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-123">Build and run it using the  `docker build` and `docker run` commands.</span></span> <span data-ttu-id="647f8-124">Docker 지원을 사용 하 여 Azure Functions 빌드를 시작 하는 자세한 단계는 [사용자 지정 이미지를 사용 하 여 Linux에서 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) 자습서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="647f8-124">For detailed steps to get started building Azure Functions with Docker support, see the [Create a function on Linux using a custom image](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) tutorial.</span></span>

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a><span data-ttu-id="647f8-125">서버 리스 및 Kubernetes를 KEDA와 결합 하는 방법</span><span class="sxs-lookup"><span data-stu-id="647f8-125">How to combine serverless and Kubernetes with KEDA</span></span>

<span data-ttu-id="647f8-126">Azure 함수는 지정 된 함수를 대상으로 하는 이벤트 비율에 따라 수요를 충족 하도록 자동으로 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-126">Azure functions scale automatically to meet demand based on the rate of events that are targeting a given function.</span></span> <span data-ttu-id="647f8-127">또한 Kubernetes를 활용 하 여 함수를 호스팅하고 Kubernetes 기반 이벤트 기반 자동 크기 조정 또는 KEDA를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-127">Additionally, you can leverage Kubernetes to host your functions and use Kubernetes-based Event Driven Autoscaling, or KEDA.</span></span> <span data-ttu-id="647f8-128">이벤트가 발생 하지 않을 때 KEDA는 0 개의 인스턴스로 확장 될 수 있으며, 이벤트에 대 한 응답으로 수평 pod autoscaler를 사용 하 여 요청에 맞게 컨테이너 수를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="647f8-128">When no events are occurring, KEDA can scale down to 0 instances, and then in response to events it can scale up the number of containers to meet the demand using its horizontal pod autoscaler.</span></span> <span data-ttu-id="647f8-129">[KEDA를 사용 하 여 Azure 함수 크기 조정에 대해 자세히 알아보세요](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).</span><span class="sxs-lookup"><span data-stu-id="647f8-129">[Learn more about scaling Azure functions with KEDA](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).</span></span>

## <a name="references"></a><span data-ttu-id="647f8-130">참조 항목</span><span class="sxs-lookup"><span data-stu-id="647f8-130">References</span></span>

- [<span data-ttu-id="647f8-131">Docker 컨테이너에서 Azure Functions 실행</span><span class="sxs-lookup"><span data-stu-id="647f8-131">Run Azure Functions in a Docker Container</span></span>](https://markheath.net/post/azure-functions-docker)
- [<span data-ttu-id="647f8-132">사용자 지정 이미지를 사용 하 여 Linux에서 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="647f8-132">Create a function on Linux using a custom image</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [<span data-ttu-id="647f8-133">Kubernetes 이벤트 기반 자동 크기 조정을 사용 하는 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="647f8-133">Azure Functions with Kubernetes Event Driven Autoscaling</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)

>[!div class="step-by-step"]
><span data-ttu-id="647f8-134">[이전](leverage-serverless-functions.md)
>[다음](deploy-containers-azure.md)</span><span class="sxs-lookup"><span data-stu-id="647f8-134">[Previous](leverage-serverless-functions.md)
[Next](deploy-containers-azure.md)</span></span>

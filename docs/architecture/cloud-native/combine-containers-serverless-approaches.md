---
title: 클라우드 네이티브 서비스에 대 한 컨테이너 및 서버를 사용 하지 않는 방식 조합
description: 서버를 사용 하지 않는 방법으로 컨테이너와 Kubernetes 결합
ms.date: 04/23/2020
ms.openlocfilehash: fe9e9fd5d07132971d64bc6433a762fb7bd22048
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199666"
---
# <a name="combining-containers-and-serverless-approaches"></a><span data-ttu-id="6f064-103">컨테이너 및 서버리스 접근 방식 결합</span><span class="sxs-lookup"><span data-stu-id="6f064-103">Combining containers and serverless approaches</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="6f064-104">클라우드 네이티브 응용 프로그램은 일반적으로 컨테이너 및 오케스트레이션을 활용 하는 서비스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-104">Cloud-native applications typically implement services leveraging containers and orchestration.</span></span> <span data-ttu-id="6f064-105">응용 프로그램의 서비스를 Azure Functions로 노출 하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-105">There are often opportunities to expose some of the application's services as Azure Functions.</span></span> <span data-ttu-id="6f064-106">그러나 Kubernetes에 배포 된 클라우드 네이티브 앱을 사용 하는 경우이 동일한 도구 집합 내에서 Azure Functions를 활용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-106">However, with a cloud-native app deployed to Kubernetes, it would be nice to leverage Azure Functions within this same toolset.</span></span> <span data-ttu-id="6f064-107">다행히 Kubernetes 기반 앱의 나머지와 동일한 프로세스 및 도구를 사용 하 여 Docker 컨테이너 내 Azure Functions을 래핑하고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-107">Fortunately, you can wrap Azure Functions inside Docker containers and deploy them using the same processes and tools as the rest of your Kubernetes-based app.</span></span>

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a><span data-ttu-id="6f064-108">서버를 사용 하지 않는 컨테이너를 사용 하는 경우는 언제 인가요?</span><span class="sxs-lookup"><span data-stu-id="6f064-108">When does it make sense to use containers with serverless?</span></span>

<span data-ttu-id="6f064-109">Azure 함수는 배포 되는 플랫폼에 대해 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-109">Your Azure Function has no knowledge of the platform on which it's deployed.</span></span> <span data-ttu-id="6f064-110">일부 시나리오에서는 특정 요구 사항이 있을 수 있으며 함수 코드가 실행 될 환경을 사용자 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-110">For some scenarios, you may have specific requirements and need to customize the environment on which your function code will run.</span></span> <span data-ttu-id="6f064-111">종속성 또는 기본 이미지에서 지원 하지 않는 구성을 지 원하는 사용자 지정 이미지가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-111">You'll need a custom image that supports dependencies or a configuration not supported by the default image.</span></span> <span data-ttu-id="6f064-112">이러한 경우 사용자 지정 Docker 컨테이너에 함수를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-112">In these cases, it makes sense to deploy your function in a custom Docker container.</span></span>

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a><span data-ttu-id="6f064-113">Azure Functions 컨테이너를 사용 하지 않는 경우는 언제 인가요?</span><span class="sxs-lookup"><span data-stu-id="6f064-113">When should you avoid using containers with Azure Functions?</span></span>

<span data-ttu-id="6f064-114">소비 청구를 사용 하려는 경우에는 컨테이너에서 함수를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-114">If you want to use consumption billing, you won't be able to run your function in a container.</span></span> <span data-ttu-id="6f064-115">또한 Kubernetes 클러스터에 함수를 배포 하는 경우에는 Azure Functions에서 제공 하는 기본 제공 크기 조정을 더 이상 활용 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-115">What's more, if you deploy your function to a Kubernetes cluster, you'll no longer benefit from the built-in scaling provided by Azure Functions.</span></span> <span data-ttu-id="6f064-116">이 챕터의 앞부분에서 설명한 Kubernetes의 크기 조정 기능을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-116">You'll need to use Kubernetes' scaling features, described earlier in this chapter.</span></span>

## <a name="how-to-combine-serverless-and-docker-containers"></a><span data-ttu-id="6f064-117">서버 리스 및 Docker 컨테이너를 결합 하는 방법</span><span class="sxs-lookup"><span data-stu-id="6f064-117">How to combine serverless and Docker containers</span></span>

<span data-ttu-id="6f064-118">Docker 컨테이너에서 Azure 함수를 래핑하려면 [Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools) 를 설치한 후 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-118">To wrap an Azure Function in a Docker container, install the [Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools) and then run the following command:</span></span>

```console
func init ProjectName --worker-runtime dotnet --docker
```

<span data-ttu-id="6f064-119">프로젝트를 만들 때 Dockerfile 및에 `dotnet`구성 된 작업자 런타임이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-119">When the project is created, it will include a Dockerfile and the worker runtime configured to `dotnet`.</span></span> <span data-ttu-id="6f064-120">이제 함수를 로컬에서 만들고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-120">Now, you can create and test your function locally.</span></span> <span data-ttu-id="6f064-121">`docker build` 및 `docker run` 명령을 사용 하 여 빌드하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-121">Build and run it using the  `docker build` and `docker run` commands.</span></span> <span data-ttu-id="6f064-122">Docker 지원을 사용 하 여 Azure Functions 빌드를 시작 하는 자세한 단계는 [사용자 지정 이미지를 사용 하 여 Linux에서 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) 자습서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f064-122">For detailed steps to get started building Azure Functions with Docker support, see the [Create a function on Linux using a custom image](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) tutorial.</span></span>

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a><span data-ttu-id="6f064-123">서버 리스 및 Kubernetes를 KEDA와 결합 하는 방법</span><span class="sxs-lookup"><span data-stu-id="6f064-123">How to combine serverless and Kubernetes with KEDA</span></span>

<span data-ttu-id="6f064-124">Azure 함수는이를 대상으로 하는 이벤트의 비율에 따라 수요를 충족 하도록 자동으로 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-124">Azure functions scale automatically to meet demand based on the rate of events that are targeting it.</span></span> <span data-ttu-id="6f064-125">언제 든 지 AKS를 활용 하 여 함수를 호스팅하고 Kubernetes 기반 이벤트 기반 자동 크기 조정 또는 KEDA를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-125">You can always leverage AKS to host your functions and use Kubernetes-based Event Driven Autoscaling, or KEDA.</span></span> <span data-ttu-id="6f064-126">이벤트가 발생 하지 않을 때 KEDA는 0 개의 인스턴스로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f064-126">When no events are occurring, KEDA can scale down to zero instances.</span></span> <span data-ttu-id="6f064-127">[KEDA를 사용 하 여 Azure 함수 크기 조정에 대해 자세히 알아보세요](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).</span><span class="sxs-lookup"><span data-stu-id="6f064-127">[Learn more about scaling Azure functions with KEDA](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6f064-128">[이전](leverage-serverless-functions.md)
>[다음](deploy-containers-azure.md)</span><span class="sxs-lookup"><span data-stu-id="6f064-128">[Previous](leverage-serverless-functions.md)
[Next](deploy-containers-azure.md)</span></span>

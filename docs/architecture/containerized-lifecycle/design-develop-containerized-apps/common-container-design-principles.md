---
title: 일반적인 컨테이너 설계 원칙
description: 적절한 컨테이너 디자인의 기본적인 원리를 알아봅니다. 이는 컨테이너를 하나의 프로세스만 호스팅해야 한다는 것입니다.
ms.date: 02/15/2019
ms.openlocfilehash: 69f3ff6c9303f0c4082695d861a8c90031295b6a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "68672500"
---
# <a name="common-container-design-principles"></a><span data-ttu-id="8d020-103">일반적인 컨테이너 설계 원칙</span><span class="sxs-lookup"><span data-stu-id="8d020-103">Common container design principles</span></span>

<span data-ttu-id="8d020-104">개발 프로세스를 시작하기 전에 컨테이너를 사용하는 방법과 관련하여 언급할 가치가 있는 몇 가지 기본 개념이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d020-104">Ahead of getting into the development process there are a few basic concepts worth mentioning with regard to how you use containers.</span></span>

## <a name="container-equals-a-process"></a><span data-ttu-id="8d020-105">컨테이너는 프로세스와 같음</span><span class="sxs-lookup"><span data-stu-id="8d020-105">Container equals a process</span></span>

<span data-ttu-id="8d020-106">컨테이너 모델에서 컨테이너는 단일 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8d020-106">In the container model, a container represents a single process.</span></span> <span data-ttu-id="8d020-107">컨테이너를 프로세스 경계로 정의하면 프로세스를 확장하거나 일괄 처리하는 데 사용되는 기본 형식을 만들기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8d020-107">By defining a container as a process boundary, you begin to create the primitives used to scale, or batch-off, processes.</span></span> <span data-ttu-id="8d020-108">Docker 컨테이너를 실행하면 [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) 정의가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d020-108">When you run a Docker container, you'll see an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) definition.</span></span> <span data-ttu-id="8d020-109">이는 컨테이너의 프로세스와 수명을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8d020-109">This defines the process and the lifetime of the container.</span></span> <span data-ttu-id="8d020-110">프로세스가 완료되면 컨테이너 수명 주기가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d020-110">When the process completes, the container life-cycle ends.</span></span> <span data-ttu-id="8d020-111">웹 서버와 같이 장기간 실행되는 프로세스와 일괄 처리 작업과 같은 단기 실행 프로세스가 있습니다. 이는 Microsoft Azure [WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/)로 구현되었을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d020-111">There are long-running processes, such as web servers, and short-lived processes, such as batch jobs, which might have been implemented as Microsoft Azure [WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/).</span></span> <span data-ttu-id="8d020-112">프로세스에 실패할 경우 컨테이너가 종료되며 조정자가 이어서 프로세스를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="8d020-112">If the process fails, the container ends, and the orchestrator takes over.</span></span> <span data-ttu-id="8d020-113">오케스트레이터가 5개의 인스턴스를 계속 실행하도록 지시받은 경우, 한 인스턴스가 실패하면 오케스트레이터는 실패한 프로세스를 대체할 컨테이너를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8d020-113">If the orchestrator was instructed to keep five instances running and one fails, the orchestrator will create another container to replace the failed process.</span></span> <span data-ttu-id="8d020-114">일괄 작업에서 프로세스는 매개 변수와 함께 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d020-114">In a batch job, the process is started with parameters.</span></span> <span data-ttu-id="8d020-115">프로세스가 완료되면 작업이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d020-115">When the process completes, the work is complete.</span></span>

<span data-ttu-id="8d020-116">여러 프로세스를 단일 컨테이너에서 실행하려는 시나리오를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d020-116">You might find a scenario in which you want multiple processes running in a single container.</span></span> <span data-ttu-id="8d020-117">모든 아키텍처 문서에는 "never"는 절대 없고 "always"도 항상 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d020-117">In any architecture document, there's never a "never," nor is there always an "always."</span></span> <span data-ttu-id="8d020-118">여러 프로세스가 필요한 시나리오의 경우 일반적인 패턴은 [Supervisor](http://supervisord.org/)를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8d020-118">For scenarios requiring multiple processes, a common pattern is to use [Supervisor](http://supervisord.org/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8d020-119">[이전](design-docker-applications.md)
>[다음](monolithic-applications.md)</span><span class="sxs-lookup"><span data-stu-id="8d020-119">[Previous](design-docker-applications.md)
[Next](monolithic-applications.md)</span></span>

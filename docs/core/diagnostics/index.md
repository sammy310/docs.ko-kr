---
title: 진단 도구 개요 - .NET Core
description: .NET Core 애플리케이션을 진단하는 데 사용할 수 있는 도구 및 기술에 대한 개요입니다.
author: sdmaclea
ms.author: stmaclea
ms.date: 08/05/2019
ms.topic: overview
ms.openlocfilehash: f107d15fa5584bb5a4834b5f11f1096bec7eb749
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974151"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="2c6fd-103">.NET Core에서 사용할 수 있는 진단 도구는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="2c6fd-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="2c6fd-104">소프트웨어가 항상 예상한 대로 작동하지는 않지만 .NET Core에는 이러한 문제를 빠르고 효과적으로 진단할 수 있는 도구 및 API가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="2c6fd-105">이 문서는 필요한 다양한 도구를 찾는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggersmanaged-debuggersmd"></a>[<span data-ttu-id="2c6fd-106">관리형 디버거</span><span class="sxs-lookup"><span data-stu-id="2c6fd-106">Managed debuggers</span></span>](managed-debuggers.md)
<span data-ttu-id="2c6fd-107">관리형 디버거를 사용하여 프로그램과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-107">Managed debuggers allow you to interact with your program.</span></span> <span data-ttu-id="2c6fd-108">일시 중지, 증분 실행, 검사 및 다시 시작은 코드 동작에 대한 인사이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="2c6fd-109">디버거는 쉽게 재현될 수 있는 기능 문제를 진단하는 데 사용되는 첫 번째 선택 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracinglogging-tracingmd"></a>[<span data-ttu-id="2c6fd-110">로깅 및 추적</span><span class="sxs-lookup"><span data-stu-id="2c6fd-110">Logging and tracing</span></span>](logging-tracing.md)
<span data-ttu-id="2c6fd-111">로깅 및 추적은 관련된 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-111">Logging and tracing are related techniques.</span></span> <span data-ttu-id="2c6fd-112">계측 코드를 참조하여 로그 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="2c6fd-113">파일에는 프로그램에서 수행하는 작업에 대한 세부 정보가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-113">The files record the details of what a program does.</span></span> <span data-ttu-id="2c6fd-114">해당 세부 정보를 사용하여 가장 복잡한 문제를 진단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="2c6fd-115">타임스탬프와 결합할 경우 이러한 기술은 성능 조사에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testingtestingindexmd"></a>[<span data-ttu-id="2c6fd-116">유닛 테스트</span><span class="sxs-lookup"><span data-stu-id="2c6fd-116">Unit testing</span></span>](../testing/index.md)
<span data-ttu-id="2c6fd-117">유닛 테스트는 고품질 소프트웨어의 연속 통합 및 배포를 위한 핵심 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-117">Unit testing is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="2c6fd-118">단위 테스트는 항목을 중단할 때 조기 경고를 제공하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-118">Unit tests are designed to give you an early warning when you break something.</span></span>

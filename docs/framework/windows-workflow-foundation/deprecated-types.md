---
description: '자세한 정보: Windows Workflow Foundation에서 사용 되지 않는 형식'
title: Windows Workflow Foundation에서 사용되지 않는 형식
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: a536f67708c5913040848df52f178dcc2a361f6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742435"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a><span data-ttu-id="1a998-103">Windows Workflow Foundation에서 사용되지 않는 형식</span><span class="sxs-lookup"><span data-stu-id="1a998-103">Deprecated types in Windows Workflow Foundation</span></span>

<span data-ttu-id="1a998-104">.NET 4에서 워크플로 팀은 <xref:System.Activities> 네임스페이스에 완전히 새로운 워크플로 엔진을 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="1a998-104">In .NET 4 the Workflow Team released an all new Workflow engine in the <xref:System.Activities> namespace.</span></span> <span data-ttu-id="1a998-105">.NET Framework 4.5 Beta 릴리스에서는 "WF 3", 및 네임 스페이스에 있는 대부분의 형식을 <xref:System.Workflow.Activities> <xref:System.Workflow.ComponentModel>  <xref:System.Workflow.Runtime> 사용 되지 않는 것으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a998-105">With the release of .NET Framework 4.5 Beta we are marking most of the types in the "WF 3" <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, and  <xref:System.Workflow.Runtime> namespaces as obsolete.</span></span>

## <a name="obsolete-namespaces-and-tools"></a><span data-ttu-id="1a998-106">사용되지 않는 네임스페이스 및 도구</span><span class="sxs-lookup"><span data-stu-id="1a998-106">Obsolete namespaces and tools</span></span>

 <span data-ttu-id="1a998-107">다음 어셈블리에는 더 이상 사용되지 않는 하나 이상의 공용 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a998-107">The following assemblies have one or more public types that will be deprecated:</span></span>

- <span data-ttu-id="1a998-108">System.Workflow.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="1a998-108">System.Workflow.Activities.dll</span></span>

- <span data-ttu-id="1a998-109">System.Workflow.ComponentModel.dll</span><span class="sxs-lookup"><span data-stu-id="1a998-109">System.Workflow.ComponentModel.dll</span></span>

- <span data-ttu-id="1a998-110">System.Workflow.Runtime.dll</span><span class="sxs-lookup"><span data-stu-id="1a998-110">System.Workflow.Runtime.dll</span></span>

- <span data-ttu-id="1a998-111">System.WorkflowServices.dll</span><span class="sxs-lookup"><span data-stu-id="1a998-111">System.WorkflowServices.dll</span></span>

- <span data-ttu-id="1a998-112">Microsoft.Workflow.DebugController.dll</span><span class="sxs-lookup"><span data-stu-id="1a998-112">Microsoft.Workflow.DebugController.dll</span></span>

- <span data-ttu-id="1a998-113">Microsoft.Workflow.Compiler.exe</span><span class="sxs-lookup"><span data-stu-id="1a998-113">Microsoft.Workflow.Compiler.exe</span></span>

- <span data-ttu-id="1a998-114">Wfc.exe</span><span class="sxs-lookup"><span data-stu-id="1a998-114">Wfc.exe</span></span>

 <span data-ttu-id="1a998-115">따라서 고객이 더 이상 사용되지 않는 WF 3 API를 사용 중인 경우 다음과 유사한 메시지가 있는 빌드 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a998-115">As a result, customers who are using the deprecated WF 3 APIs will encounter build warnings with a message similar to the following:</span></span>

 <span data-ttu-id="1a998-116">**경고 BC40000: X는 사용 되지 않습니다. WF 3 형식은 사용 되지 않습니다. 대신 WF 4를 사용 하세요.**</span><span class="sxs-lookup"><span data-stu-id="1a998-116">**Warning BC40000: X is obsolete: WF 3 types are deprecated. Please use WF 4 instead.**</span></span> <span data-ttu-id="1a998-117">이후에 릴리스되는 .NET Framework에서는 이러한 형식을 제거하겠지만, 아직 정확한 시간은 결정되지 않았습니다(4.5에서는 아님).</span><span class="sxs-lookup"><span data-stu-id="1a998-117">We will remove the types from the .NET Framework in a future release, but we have not yet determined that timeframe (not in 4.5).</span></span> <span data-ttu-id="1a998-118">현재 단계에서는 고객에게 이러한 방침을 전달하여 새로운 WF4 모델로 이동할 수 있는 충분한 시간을 주어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a998-118">This current step allows us to communicate our direction to our customers and allow them plenty of time to move to the new WF4 model.</span></span> <span data-ttu-id="1a998-119">물론 [Microsoft 지원 수명 주기 정책](/lifecycle/)에 따라 이러한 WF 3 형식을 계속 지원할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="1a998-119">We will, of course, continue to support these WF 3 types under the [Microsoft Support Lifecycle Policy](/lifecycle/).</span></span> <span data-ttu-id="1a998-120">기존 WF3 응용 프로그램은 .NET Framework 4.5에서 문제 없이 실행 되 고 Visual Studio 2012은 새로운 및 기존 WF3 기반 솔루션을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a998-120">Existing WF3 applications will run without issue on .NET Framework 4.5, and Visual Studio 2012 will support new and existing WF3-based solutions.</span></span>

 <span data-ttu-id="1a998-121">WF 4.5에서 대체되지 않은 <xref:System.Workflow.Activities.Rules> 네임스페이스의 규칙 관련 형식은 계속 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a998-121">Rules related types in the <xref:System.Workflow.Activities.Rules> namespace, which do not have a replacement in WF 4.5, have not been deprecated.</span></span>

 <span data-ttu-id="1a998-122">응용 프로그램을 WF 4로 마이그레이션하려는 고객은 [워크플로 4 마이그레이션 지침](migration-guidance.md)에 대 한 도움말을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a998-122">Customers who want to migrate their applications to WF 4 will find help in the [Workflow 4 Migration Guidance](migration-guidance.md).</span></span>

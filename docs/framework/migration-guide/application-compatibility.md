---
title: 런타임 및 대상 다시 지정 변경 내용 - .NET Framework
description: .NET Framework의 애플리케이션 호환성과 이 호환성이 다른 버전으로 마이그레이션할 때 런타임 및 대상 다시 지정 변경 내용에 어떻게 영향을 받는지에 대해 알아봅니다.
ms.date: 10/29/2019
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
ms.openlocfilehash: 26f36dd34c6c5ecae8fc5ab373ff60d9e56f8245
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475491"
---
# <a name="application-compatibility-in-the-net-framework"></a><span data-ttu-id="78e58-103">.NET Framework의 애플리케이션 호환성</span><span class="sxs-lookup"><span data-stu-id="78e58-103">Application compatibility in the .NET Framework</span></span>

<span data-ttu-id="78e58-104">호환성은 각 .NET 릴리스의 중요한 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-104">Compatibility is an important goal of each .NET release.</span></span> <span data-ttu-id="78e58-105">호환성이 있으면 각 버전이 누적되므로 이전 버전이 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-105">Compatibility ensures that each version is additive, so previous versions will continue to work.</span></span> <span data-ttu-id="78e58-106">반면, 예를 들어 성능 향상, 보안 문제 해결 또는 버그 수정을 위해 이전 기능이 변경되면 이후 버전에서 실행되는 기존 코드 또는 기존 애플리케이션에서 호환성 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-106">On the other hand, changes to previous functionality (for example, to improve performance, address security issues, or fix bugs) can cause compatibility problems in existing code or existing applications that run under a later version.</span></span>

<span data-ttu-id="78e58-107">각 앱은 다음을 통해 .NET Framework의 특정 버전을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-107">Each app targets a specific version of the .NET Framework by:</span></span>

- <span data-ttu-id="78e58-108">Visual Studio에서 대상 프레임워크 정의</span><span class="sxs-lookup"><span data-stu-id="78e58-108">Defining a target framework in Visual Studio.</span></span>
- <span data-ttu-id="78e58-109">프로젝트 파일에서 대상 프레임워크 지정</span><span class="sxs-lookup"><span data-stu-id="78e58-109">Specifying the target framework in a project file.</span></span>
- <span data-ttu-id="78e58-110">소스 코드에 <xref:System.Runtime.Versioning.TargetFrameworkAttribute> 적용</span><span class="sxs-lookup"><span data-stu-id="78e58-110">Applying a <xref:System.Runtime.Versioning.TargetFrameworkAttribute> to the source code.</span></span>

<span data-ttu-id="78e58-111">한 버전의 .NET Framework에서 다른 버전으로 마이그레이션할 때는 다음과 같은 두 가지 변경 유형을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-111">When migrating from one version of the .NET Framework to another, there are two types of changes to consider:</span></span>

- [<span data-ttu-id="78e58-112">런타임 변경 내용</span><span class="sxs-lookup"><span data-stu-id="78e58-112">Runtime changes</span></span>](#runtime-changes)
- [<span data-ttu-id="78e58-113">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="78e58-113">Retargeting changes</span></span>](#retargeting-changes)

## <a name="runtime-changes"></a><span data-ttu-id="78e58-114">런타임 변경 내용</span><span class="sxs-lookup"><span data-stu-id="78e58-114">Runtime changes</span></span>

<span data-ttu-id="78e58-115">런타임 문제는 새 런타임이 컴퓨터에서 발생하고 앱의 동작이 변경되는 경우 발생하는 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-115">Runtime issues are those that arise when a new runtime is placed on a machine and an app's behavior changes.</span></span> <span data-ttu-id="78e58-116">대상으로 지정된 버전보다 더 새로운 버전에서 실행될 경우 .NET Framework는 *quirked* 동작을 사용하여 대상으로 지정된 이전 버전을 모방합니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-116">When running on a newer version than what was targeted, the .NET Framework uses *quirked* behavior to mimic the older targeted version.</span></span> <span data-ttu-id="78e58-117">앱은 최신 버전에서 실행되지만 이전 버전에서 실행되는 것처럼 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-117">The app runs on the newer version but acts as if it's running on the older version.</span></span> <span data-ttu-id="78e58-118">.NET Framework 버전 간의 대부분의 호환성 문제는 이 특수 모델을 통해 완화됩니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-118">Many of the compatibility issues between versions of the .NET Framework are mitigated through this quirking model.</span></span> <span data-ttu-id="78e58-119">예를 들어 .NET Framework 4.0에 대해 이진이 컴파일되었지만 .NET Framework 4.5 이상이 설정된 컴퓨터에서 실행되는 경우 .NET Framework 4.0 호환 모드에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-119">For example, if a binary was compiled for .NET Framework 4.0 but runs on a machine with .NET Framework 4.5 or later, it runs in .NET Framework 4.0 compatibility mode.</span></span> <span data-ttu-id="78e58-120">즉, 최신 버전의 많은 변경 내용은 이진에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-120">This means that many of the changes in the later version don't affect the binary.</span></span>

<span data-ttu-id="78e58-121">애플리케이션의 대상이 되는 .NET Framework 버전은 코드가 실행되는 애플리케이션 도메인의 항목 어셈블리의 대상 버전에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-121">The version of the .NET Framework that an application targets is determined by the target version of the entry assembly for the application domain that the code runs in.</span></span> <span data-ttu-id="78e58-122">해당 애플리케이션 도메인에 로드된 모든 추가 어셈블리는 이 버전을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-122">All additional assemblies loaded in that application domain target that version.</span></span> <span data-ttu-id="78e58-123">예를 들어, 실행 파일의 경우, 실행 파일의 대상 버전은 해당 애플리케이션 도메인의 모든 어셈블리가 실행되는 호환 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-123">For example, in the case of an executable, the version that the executable targets is the compatibility mode all assemblies in that application domain run under.</span></span>

<span data-ttu-id="78e58-124">사용자 환경에 적용되는 런타임 변경 내용 목록을 보려면 현재 대상으로 하는 .NET Framework 버전을 선택하고 마이그레이션할 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-124">To see a list of runtime changes that apply to your environment, select the .NET Framework version you're currently targeting and then the version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](../../../includes/migration-guide/runtime/versionselector.md)]

## <a name="retargeting-changes"></a><span data-ttu-id="78e58-125">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="78e58-125">Retargeting changes</span></span>

<span data-ttu-id="78e58-126">대상 다시 지정 변경 내용은 새 버전을 대상으로 하는 어셈블리를 다시 컴파일할 때 발생하는 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-126">Retargeting changes are those that arise when an assembly is recompiled to target a newer version.</span></span> <span data-ttu-id="78e58-127">새 버전으로 대상을 지정하면 어셈블리는 이전 기능에 대한 잠재적인 호환성 문제뿐 아니라 새로운 기능을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-127">Targeting a newer version means the assembly opts into the new features as well as potential compatibility issues for old features.</span></span>

<span data-ttu-id="78e58-128">사용자 환경에 적용되는 대상 다시 지정 변경 내용 목록을 보려면 현재 대상으로 하는 .NET Framework 버전을 선택하고 마이그레이션할 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-128">To see a list of retargeting changes that apply to your environment, select the .NET Framework version you're currently targeting and then the version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](../../../includes/migration-guide/retargeting/versionselector.md)]

## <a name="impact-classification"></a><span data-ttu-id="78e58-129">영향 분류</span><span class="sxs-lookup"><span data-stu-id="78e58-129">Impact classification</span></span>

<span data-ttu-id="78e58-130">런타임 및 대상 다시 지정 변경 내용을 설명하는 주제(예: [4.7.2에서 4.8로 마이그레이션에 대한 대상 다시 지정 변경 내용](retargeting/4.7.2-4.8.md))에서 개별 항목은 다음과 같이 예상되는 영향별로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-130">In the topics that describe runtime and retargeting changes, for example, [Retargeting changes for migrating from 4.7.2 to 4.8](retargeting/4.7.2-4.8.md), individual items are classified by their expected impact as follows:</span></span>

<span data-ttu-id="78e58-131">**Major**</span><span class="sxs-lookup"><span data-stu-id="78e58-131">**Major**</span></span>\
<span data-ttu-id="78e58-132">다수의 앱에 영향을 주거나 코드를 대폭 수정해야 하는 중요한 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-132">A significant change that affects a large number of apps or that requires substantial modification of code.</span></span>

<span data-ttu-id="78e58-133">**Minor**</span><span class="sxs-lookup"><span data-stu-id="78e58-133">**Minor**</span></span>\
<span data-ttu-id="78e58-134">소수의 앱에 영향을 주거나 코드를 약간만 수정해야 하는 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-134">A change that affects a small number of apps or that requires minor modification of code.</span></span>

<span data-ttu-id="78e58-135">**특별한 경우**</span><span class="sxs-lookup"><span data-stu-id="78e58-135">**Edge case**</span></span>\
<span data-ttu-id="78e58-136">일반적이지 않은 매우 특별한 시나리오의 앱에 영향을 주는 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-136">A change that affects apps under very specific scenarios that are not common.</span></span>

<span data-ttu-id="78e58-137">**투명**</span><span class="sxs-lookup"><span data-stu-id="78e58-137">**Transparent**</span></span>\
<span data-ttu-id="78e58-138">앱 개발자나 사용자에게 뚜렷한 영향을 주지 않는 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-138">A change that has no noticeable effect on the app's developer or user.</span></span> <span data-ttu-id="78e58-139">이 변경 내용으로 인한 앱 수정은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78e58-139">The app should not require modification because of this change.</span></span>

## <a name="see-also"></a><span data-ttu-id="78e58-140">참조</span><span class="sxs-lookup"><span data-stu-id="78e58-140">See also</span></span>

- [<span data-ttu-id="78e58-141">버전 및 종속성</span><span class="sxs-lookup"><span data-stu-id="78e58-141">Versions and dependencies</span></span>](versions-and-dependencies.md)
- [<span data-ttu-id="78e58-142">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="78e58-142">What's new</span></span>](../whats-new/index.md)
- [<span data-ttu-id="78e58-143">사용되지 않는 기능</span><span class="sxs-lookup"><span data-stu-id="78e58-143">What's obsolete</span></span>](../whats-new/whats-obsolete.md)

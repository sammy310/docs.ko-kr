---
title: 호환성
description: 코드 변경이 .NET의 호환성에 미칠 수 있는 영향을 알아봅니다.
ms.date: 06/10/2019
ms.openlocfilehash: 1cf14b7ff4143367653bd1c305cc1dda6711f980
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415695"
---
# <a name="how-code-changes-can-affect-compatibility"></a><span data-ttu-id="a4ed3-103">코드 변경이 호환성에 미칠 수 있는 영향</span><span class="sxs-lookup"><span data-stu-id="a4ed3-103">How code changes can affect compatibility</span></span>

<span data-ttu-id="a4ed3-104">‘호환성’은 원래 코드를 개발한 .NET 구현 버전이 아닌 다른 버전에서 코드를 컴파일하거나 실행하는 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-104">*Compatibility* refers to the ability to compile or execute code on a version of a .NET implementation other than the one with which the code was originally developed.</span></span> <span data-ttu-id="a4ed3-105">[특정 변경 내용](index.md)은 6가지 측면에서 호환성에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-105">A [particular change](index.md) can affect compatibility in six different ways:</span></span>

- [<span data-ttu-id="a4ed3-106">동작 변경</span><span class="sxs-lookup"><span data-stu-id="a4ed3-106">Behavioral change</span></span>](#behavioral-change)
- [<span data-ttu-id="a4ed3-107">이진 호환성</span><span class="sxs-lookup"><span data-stu-id="a4ed3-107">Binary compatibility</span></span>](#binary-compatibility)
- [<span data-ttu-id="a4ed3-108">소스 호환성</span><span class="sxs-lookup"><span data-stu-id="a4ed3-108">Source compatibility</span></span>](#source-compatibility)
- [<span data-ttu-id="a4ed3-109">디자인 타임 호환성</span><span class="sxs-lookup"><span data-stu-id="a4ed3-109">Design-time compatibility</span></span>](#design-time-compatibility)
- [<span data-ttu-id="a4ed3-110">이전 버전과의 호환성</span><span class="sxs-lookup"><span data-stu-id="a4ed3-110">Backwards compatibility</span></span>](#backwards-compatibility)
- <span data-ttu-id="a4ed3-111">[이후 버전과의 호환성](#forward-compatibility)(.NET Core의 목표는 아님)</span><span class="sxs-lookup"><span data-stu-id="a4ed3-111">[Forward compatibility](#forward-compatibility) (not a goal of .NET Core)</span></span>

## <a name="behavioral-change"></a><span data-ttu-id="a4ed3-112">동작 변경</span><span class="sxs-lookup"><span data-stu-id="a4ed3-112">Behavioral change</span></span>

<span data-ttu-id="a4ed3-113">동작 변경은 멤버의 동작 변경을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-113">A behavioral change represents a change to the behavior of a member.</span></span> <span data-ttu-id="a4ed3-114">변경은 외부적으로 표시되거나(예: 메서드가 다른 예외를 throw할 수 있음), 변경된 구현을 나타낼 수도 있습니다(예: 반환 값이 계산되는 방식 변경, 내부 메서드 호출 추가 또는 제거, 중요한 성능 향상).</span><span class="sxs-lookup"><span data-stu-id="a4ed3-114">The change may be externally visible (for example, a method may throw a different exception), or it may represent a changed implementation (for example, a change in the way a return value is calculated, the addition or removal of internal method calls, or even a significant performance improvement).</span></span>

<span data-ttu-id="a4ed3-115">동작 변경이 외부적으로 표시되고 형식의 공용 계약을 수정하는 경우 이진 호환성에 영향을 주기 때문에 쉽게 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-115">When behavioral changes are externally visible and modify a type's public contract, they are easy to evaluate since they affect binary compatibility.</span></span> <span data-ttu-id="a4ed3-116">구현 변경은 평가하기가 훨씬 더 어렵습니다. 변경의 특성과 API 사용의 빈도 및 패턴에 따라 변경의 영향은 심각한 수준에서 위험하지 않은 수준까지 이를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-116">Implementation changes are much more difficult to evaluate; depending on the nature of the change and the frequency and patterns of use of the API, the impact of a change can range from severe to innocuous.</span></span>

## <a name="binary-compatibility"></a><span data-ttu-id="a4ed3-117">이진 호환성</span><span class="sxs-lookup"><span data-stu-id="a4ed3-117">Binary compatibility</span></span>

<span data-ttu-id="a4ed3-118">이진 호환성은 API 소비자가 다시 컴파일하지 않고 최신 버전에서 API를 사용하는 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-118">Binary compatibility refers to the ability of a consumer of an API to use the API on a newer version without recompilation.</span></span> <span data-ttu-id="a4ed3-119">형식에 메서드를 추가하거나 새 인터페이스 구현을 추가할 때 이 변경은 이진 호환성에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-119">Such changes as adding methods or adding a new interface implementation to a type do not affect binary compatibility.</span></span> <span data-ttu-id="a4ed3-120">그러나 소비자가 어셈블리에 의해 공개된 동일한 인터페이스에 더 이상 액세스할 수 없도록 어셈블리의 공용 시그니처를 제거하거나 변경하면 이진 호환성에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-120">However, removing or altering an assembly's public signatures so that consumers can no longer access the same interface exposed by the assembly does affect binary compatibility.</span></span> <span data-ttu-id="a4ed3-121">이런 종류의 변경을 ‘이진과 호환되지 않는 변경’이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-121">A change of this kind is termed a *binary incompatible change*.</span></span>

## <a name="source-compatibility"></a><span data-ttu-id="a4ed3-122">소스 호환성</span><span class="sxs-lookup"><span data-stu-id="a4ed3-122">Source compatibility</span></span>

<span data-ttu-id="a4ed3-123">소스 호환성은 기존 API 소비자가 소스 변경 없이 최신 버전에서 다시 컴파일되는 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-123">Source compatibility refers to the ability of existing consumers of an API to recompile against a newer version without any source changes.</span></span> <span data-ttu-id="a4ed3-124">‘소스와 호환되지 않는 변경’은 소비자가 상위 버전의 API에 대해 변경을 성공적으로 빌드하기 위해 소스 코드를 수정해야 하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-124">A *source incompatible change* occurs when a consumer needs to modify source code for it to build successfully against a newer version of an API.</span></span>

## <a name="design-time-compatibility"></a><span data-ttu-id="a4ed3-125">디자인 타임 호환성</span><span class="sxs-lookup"><span data-stu-id="a4ed3-125">Design-time compatibility</span></span>

<span data-ttu-id="a4ed3-126">디자인 타임 호환성은 Visual Studio 및 기타 디자인 타임 환경의 버전 간에 디자인 타임 환경을 유지하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-126">Design-time compatibility refers to preserving the design-time experience across versions of Visual Studio and other design-time environments.</span></span> <span data-ttu-id="a4ed3-127">디자이너의 동작이나 UI가 이 호환성에 영향을 주지만, 디자인 타임 호환성의 가장 중요한 측면은 프로젝트 호환성과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-127">While this can involve the behavior or the UI of designers, the most important aspect of design-time compatibility concerns project compatibility.</span></span> <span data-ttu-id="a4ed3-128">프로젝트 또는 솔루션을 디자인 타임 환경의 최신 버전에서 열고 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-128">A project or solution must be able to be opened and used on a newer version of the design-time environment.</span></span>

## <a name="backwards-compatibility"></a><span data-ttu-id="a4ed3-129">이전 버전과의 호환성</span><span class="sxs-lookup"><span data-stu-id="a4ed3-129">Backwards compatibility</span></span>

<span data-ttu-id="a4ed3-130">이전 버전과의 호환성은 기존 API 소비자가 동일한 방식으로 동작하면서 새 버전에서 실행되는 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-130">Backwards compatibility refers to the ability of an existing consumer of an API to run against a new version while behaving in the same way.</span></span> <span data-ttu-id="a4ed3-131">동작 변경 및 이진 호환성 변경은 둘 다 이전 버전과의 호환성에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-131">Both behavioral changes and changes in binary compatibility affect backwards compatibility.</span></span> <span data-ttu-id="a4ed3-132">소비자가 최신 버전의 API에서 실행될 수 없거나 실행될 때 다르게 동작하는 경우 이 API는 ‘이전 버전과 호환되지 않습니다’.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-132">If a consumer is not able to run or behaves differently when running against the newer version of the API, the API is *backwards incompatible*.</span></span>

<span data-ttu-id="a4ed3-133">개발자는 최신 버전의 API에서 이전 버전과의 호환성을 기대하므로 이전 버전과의 호환성에 영향을 주는 변경은 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-133">Changes that affect backwards compatibility are discouraged, since developers expect backwards compatibility in newer versions of an API.</span></span>

## <a name="forward-compatibility"></a><span data-ttu-id="a4ed3-134">이후 버전과의 호환성</span><span class="sxs-lookup"><span data-stu-id="a4ed3-134">Forward compatibility</span></span>

<span data-ttu-id="a4ed3-135">이후 버전과의 호환성은 기존 API 소비자가 동일한 동작을 나타내면서 이전 버전에서 실행되는 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-135">Forward compatibility refers to the ability of an existing consumer of an API to run against an older version while exhibiting the same behavior.</span></span> <span data-ttu-id="a4ed3-136">소비자가 이전 버전의 API에서 실행될 수 없거나 실행될 때 다르게 동작하는 경우 이 API는 ‘이후 버전과 호환되지 않습니다’.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-136">If a consumer is not able to run or behaves differently when run against an older version of the API, the API is *forward incompatible*.</span></span>

<span data-ttu-id="a4ed3-137">이후 버전과의 호환성을 유지하면 실제로 버전 간에 변경하거나 추가하는 것이 불가능합니다. 해당 변경으로 인해 이후 버전을 대상으로 하는 소비자가 이전 버전에서 실행될 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-137">Maintaining forward compatibility virtually precludes any changes or additions from version to version, since those changes prevent a consumer that targets a later version from running under an earlier version.</span></span> <span data-ttu-id="a4ed3-138">개발자는 최신 API를 사용하는 소비자가 이전 API에서 제대로 작동하지 않을 것이라고 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-138">Developers expect that a consumer that relies on a newer API may not function correctly against the older API.</span></span>

<span data-ttu-id="a4ed3-139">이후 버전과의 호환성을 유지하는 것은 .NET Core의 목표가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-139">Maintaining forward compatibility is not a goal of .NET Core.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4ed3-140">참조</span><span class="sxs-lookup"><span data-stu-id="a4ed3-140">See also</span></span>

- [<span data-ttu-id="a4ed3-141">.NET Core의 호환성이 손상되는 변경 평가</span><span class="sxs-lookup"><span data-stu-id="a4ed3-141">Evaluate breaking changes in .NET Core</span></span>](index.md)

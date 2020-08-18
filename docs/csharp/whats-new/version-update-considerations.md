---
title: C# 개발자를 위한 버전 및 업데이트 고려 사항
description: 라이브러리에 새로운 언어 기능을 도입하면 해당 라이브러리를 사용하는 코드에 영향을 줄 수 있습니다.
ms.topic: reference
ms.date: 09/19/2018
ms.openlocfilehash: f7db7c79792d04bcf592bc1858e1f0f05cb34402
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88268129"
---
# <a name="version-and-update-considerations-for-c-developers"></a><span data-ttu-id="d58c4-103">C# 개발자를 위한 버전 및 업데이트 고려 사항</span><span class="sxs-lookup"><span data-stu-id="d58c4-103">Version and update considerations for C# developers</span></span>

<span data-ttu-id="d58c4-104">C# 언어에 새로운 기능이 추가되므로 호환성은 매우 중요한 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-104">Compatibility is a very important goal as new features are added to the C# language.</span></span> <span data-ttu-id="d58c4-105">대부분의 경우 문제없이 새 컴파일러 버전으로 기존 코드를 다시 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-105">In almost all cases, existing code can be recompiled with a new compiler version without any issue.</span></span>

<span data-ttu-id="d58c4-106">라이브러리에서 새 언어 기능을 채택할 때는 더욱 주의해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-106">More care may be required when you adopt new language features in a library.</span></span> <span data-ttu-id="d58c4-107">최신 버전에 있는 기능을 사용하여 새 라이브러리를 만드는 경우 이전 버전의 컴파일러로 빌드된 앱이 새 라이브러리를 사용할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-107">You may be creating a new library with features found in the latest version and need to ensure apps built using previous versions of the compiler can use it.</span></span> <span data-ttu-id="d58c4-108">또는 기존 라이브러리를 업그레이드하는 경우 아직 업그레이드된 버전이 없는 사용자가 많을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-108">Or you may be upgrading an existing library and many of your users may not have upgraded versions yet.</span></span> <span data-ttu-id="d58c4-109">새 기능을 채택하기로 결정하면 소스 호환 가능 및 이진 호환 가능이라는 두 가지 호환성 변형을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-109">As you make decisions on adopting new features, you'll need to consider two variations of compatibility: source compatible and binary compatible.</span></span>

## <a name="binary-compatible-changes"></a><span data-ttu-id="d58c4-110">이진 호환 가능 변경</span><span class="sxs-lookup"><span data-stu-id="d58c4-110">Binary compatible changes</span></span>

<span data-ttu-id="d58c4-111">라이브러리를 사용하는 애플리케이션 및 라이브러리를 다시 빌드하지 않고 업데이트된 라이브러리를 사용할 수 있는 경우 라이브러리 변경은 **이진 호환 가능**합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-111">Changes to your library are **binary compatible** when your updated library can be used without rebuilding applications and libraries that use it.</span></span> <span data-ttu-id="d58c4-112">종속 어셈블리를 다시 빌드하거나 소스 코드를 변경하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-112">Dependent assemblies are not required to be rebuilt, nor are any source code changes required.</span></span> <span data-ttu-id="d58c4-113">이진 호환 가능 변경은 소스 호환 가능 변경이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-113">Binary compatible changes are also source compatible changes.</span></span>

## <a name="source-compatible-changes"></a><span data-ttu-id="d58c4-114">소스 호환 가능 변경</span><span class="sxs-lookup"><span data-stu-id="d58c4-114">Source compatible changes</span></span>

<span data-ttu-id="d58c4-115">라이브러리를 사용하는 애플리케이션 및 라이브러리에 대해 소스 코드를 변경하지 않아도 되지만 올바르게 작동하려면 새 버전에 대해 소스를 다시 컴파일해야 하는 경우 라이브러리 변경은 **소스 호환 가능**합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-115">Changes to your library are **source compatible** when applications and libraries that use your library do not require source code changes, but the source must be recompiled against the new version to work correctly.</span></span>

## <a name="incompatible-changes"></a><span data-ttu-id="d58c4-116">호환되지 않는 변경</span><span class="sxs-lookup"><span data-stu-id="d58c4-116">Incompatible changes</span></span>

<span data-ttu-id="d58c4-117">변경이 **소스 호환 가능** 또는 **이진 호환 가능**하지 않은 경우 종속 라이브러리 및 애플리케이션에서 소스 코드를 변경하고 다시 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-117">If a change is neither **source compatible** nor **binary compatible**, source code changes along with recompilation are required in dependent libraries and applications.</span></span>

## <a name="evaluate-your-library"></a><span data-ttu-id="d58c4-118">라이브러리 평가</span><span class="sxs-lookup"><span data-stu-id="d58c4-118">Evaluate your library</span></span>

<span data-ttu-id="d58c4-119">이러한 호환성 개념은 라이브러리에 대한 public 및 protected 선언에 영향을 주며 내부 구현에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-119">These compatibility concepts affect the public and protected declarations for your library, not its internal implementation.</span></span> <span data-ttu-id="d58c4-120">내부적으로 새로운 기능을 채택하면 항상 **이진 호환 가능**합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-120">Adopting any new features internally are always **binary compatible**.</span></span>  

<span data-ttu-id="d58c4-121">**이진 호환 가능** 변경은 public 선언에 대해 이전 구문과 동일한 컴파일된 코드를 생성하는 새 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-121">**Binary compatible** changes provide new syntax that generates the same compiled code for public declarations as the older syntax.</span></span> <span data-ttu-id="d58c4-122">예를 들어 메서드를 식 본문 멤버로 변경하는 것은 **이진 호환 가능** 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-122">For example, changing a method to an expression-bodied member is a **binary compatible** change:</span></span>

<span data-ttu-id="d58c4-123">원래 코드:</span><span class="sxs-lookup"><span data-stu-id="d58c4-123">Original code:</span></span>

```csharp
public double CalculateSquare(double value)
{
    return value * value;
}
```

<span data-ttu-id="d58c4-124">새로운 코드:</span><span class="sxs-lookup"><span data-stu-id="d58c4-124">New code:</span></span>

```csharp
public double CalculateSquare(double value) => value * value;
```

<span data-ttu-id="d58c4-125">**소스 호환 가능** 변경은 public 멤버에 대해 컴파일된 코드를 변경하지만 기존 호출 사이트와 호환되는 방식으로 변경하는 구문을 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-125">**Source compatible** changes introduce syntax that changes the compiled code for a public member, but in a way that is compatible with existing call sites.</span></span> <span data-ttu-id="d58c4-126">예를 들어 값 기준 매개 변수에서 `in` 참조 기준 매개 변수로 메서드 시그니처를 변경하는 것은 소스 호환 가능하지만 이진 호환 가능하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-126">For example, changing a method signature from a by value parameter to an `in` by reference parameter is source compatible, but not binary compatible:</span></span>

<span data-ttu-id="d58c4-127">원래 코드:</span><span class="sxs-lookup"><span data-stu-id="d58c4-127">Original code:</span></span>

```csharp
public double CalculateSquare(double value) => value * value;
```

<span data-ttu-id="d58c4-128">새로운 코드:</span><span class="sxs-lookup"><span data-stu-id="d58c4-128">New code:</span></span>

```csharp
public double CalculateSquare(in double value) => value * value;
```

<span data-ttu-id="d58c4-129">[새로운 기능](index.md) 문서에서는 public 선언에 영향을 주는 기능을 도입하는 것이 소스 호환 가능 또는 이진 호환 가능한지 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c4-129">The [What's new](index.md) articles note if introducing a feature that affects public declarations is source compatible or binary compatible.</span></span>

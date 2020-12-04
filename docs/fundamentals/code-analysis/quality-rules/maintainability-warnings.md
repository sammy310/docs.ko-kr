---
title: 유지 관리 규칙 (코드 분석)
description: 코드 분석 유지 관리 규칙에 대해 알아봅니다.
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- rules, maintainability
- managed code analysis rules, maintainability rules
- maintainability rules
author: gewarren
ms.author: gewarren
ms.openlocfilehash: fc2ef2b42eeba241b7af66b579a60365ad2b88c7
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "96592406"
---
# <a name="maintainability-rules"></a><span data-ttu-id="3ec8e-103">유지 관리 규칙</span><span class="sxs-lookup"><span data-stu-id="3ec8e-103">Maintainability rules</span></span>

<span data-ttu-id="3ec8e-104">유지 관리 규칙은 라이브러리 및 응용 프로그램 유지 관리를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec8e-104">Maintainability rules support library and application maintenance.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3ec8e-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="3ec8e-105">In this section</span></span>

| <span data-ttu-id="3ec8e-106">규칙</span><span class="sxs-lookup"><span data-stu-id="3ec8e-106">Rule</span></span> | <span data-ttu-id="3ec8e-107">설명</span><span class="sxs-lookup"><span data-stu-id="3ec8e-107">Description</span></span> |
|-----------|-----------------------------------|
| [<span data-ttu-id="3ec8e-108">CA1501: 상속성을 너무 많이 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3ec8e-108">CA1501: Avoid excessive inheritance</span></span>](ca1501.md) | <span data-ttu-id="3ec8e-109">형식이 상속 계층 구조에서 네 단계보다 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ec8e-109">A type is more than four levels deep in its inheritance hierarchy.</span></span> <span data-ttu-id="3ec8e-110">여러 번 중첩된 형식 계층 구조는 추적하고, 이해하고, 유지 관리하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="3ec8e-110">Deeply nested type hierarchies can be difficult to follow, understand, and maintain.</span></span> |
| [<span data-ttu-id="3ec8e-111">CA1502: 지나치게 복잡하게 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3ec8e-111">CA1502: Avoid excessive complexity</span></span>](ca1502.md) | <span data-ttu-id="3ec8e-112">이 규칙은 메서드를 통과하는 선형 독립 경로의 수를 측정하며 조건부 분기의 수와 복잡성에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ec8e-112">This rule measures the number of linearly independent paths through the method, which is determined by the number and complexity of conditional branches.</span></span> |
| [<span data-ttu-id="3ec8e-113">CA1505: 유지 관리할 수 없는 코드를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3ec8e-113">CA1505: Avoid unmaintainable code</span></span>](ca1505.md) | <span data-ttu-id="3ec8e-114">형식 또는 메서드에 낮은 유지 관리 인덱스 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ec8e-114">A type or method has a low maintainability index value.</span></span> <span data-ttu-id="3ec8e-115">낮은 유지 관리 인덱스는 형식 또는 메서드가 유지 관리하기 어렵고 다시 디자인될 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3ec8e-115">A low maintainability index indicates that a type or method is probably difficult to maintain and would be a good candidate for redesign.</span></span> |
| [<span data-ttu-id="3ec8e-116">CA1506: 클래스를 지나치게 많이 결합하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3ec8e-116">CA1506: Avoid excessive class coupling</span></span>](ca1506.md) | <span data-ttu-id="3ec8e-117">이 규칙은 형식 또는 메서드에 들어 있는 고유한 형식 참조의 개수를 계산하여 클래스 결합을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec8e-117">This rule measures class coupling by counting the number of unique type references that a type or method contains.</span></span> |
| [<span data-ttu-id="3ec8e-118">CA1507: 문자열 대신 nameof 사용</span><span class="sxs-lookup"><span data-stu-id="3ec8e-118">CA1507: Use nameof in place of string</span></span>](ca1507.md) | <span data-ttu-id="3ec8e-119">문자열 리터럴은 식을 사용할 수 있는 인수로 사용 됩니다 `nameof` .</span><span class="sxs-lookup"><span data-stu-id="3ec8e-119">A string literal is used as an argument where a `nameof` expression could be used.</span></span> |
| [<span data-ttu-id="3ec8e-120">CA1508: 데드 조건부 코드 방지</span><span class="sxs-lookup"><span data-stu-id="3ec8e-120">CA1508: Avoid dead conditional code</span></span>](ca1508.md) | <span data-ttu-id="3ec8e-121">메서드에는 항상 `true` 또는 런타임 시로 계산 되는 조건부 코드가 있습니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="3ec8e-121">A method has conditional code that always evaluates to `true` or `false` at runtime.</span></span> <span data-ttu-id="3ec8e-122">이렇게 하면 조건의 분기에서 데드 코드가 발생 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec8e-122">This leads to dead code in the `false` branch of the condition.</span></span> |
| [<span data-ttu-id="3ec8e-123">CA1509: 코드 메트릭 구성 파일의 잘못된 항목</span><span class="sxs-lookup"><span data-stu-id="3ec8e-123">CA1509: Invalid entry in code metrics configuration file</span></span>](ca1509.md) | <span data-ttu-id="3ec8e-124">[CA1501](ca1501.md), [CA1502](ca1502.md), [CA1505](ca1505.md) 및 [CA1506](ca1506.md)와 같은 코드 메트릭 규칙에서 `CodeMetricsConfig.txt` 잘못 된 항목을 포함 하는 이라는 구성 파일을 제공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3ec8e-124">Code metrics rules, such as [CA1501](ca1501.md), [CA1502](ca1502.md), [CA1505](ca1505.md) and [CA1506](ca1506.md), supplied a configuration file named `CodeMetricsConfig.txt` that has an invalid entry.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3ec8e-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ec8e-125">See also</span></span>

- [<span data-ttu-id="3ec8e-126">관리 코드의 복잡성 및 유지 관리 용이성 측정</span><span class="sxs-lookup"><span data-stu-id="3ec8e-126">Measure Complexity and Maintainability of Managed Code</span></span>](/visualstudio/code-quality/code-metrics-values)

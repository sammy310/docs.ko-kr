---
title: 불필요한 코드 규칙
description: 코드 분석 불필요 한 코드 규칙에 대 한 자세한 정보
ms.date: 09/30/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
ms.openlocfilehash: 16c4ba0e4bee2388736bf9813a3e8290d8d4da32
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "96593859"
---
# <a name="unnecessary-code-rules"></a><span data-ttu-id="54560-103">불필요한 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="54560-103">Unnecessary code rules</span></span>

<span data-ttu-id="54560-104">불필요 한 코드 규칙은 코드 베이스에서 불필요 하 고 리팩터링 또는 제거할 수 있는 여러 부분을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="54560-104">Unnecessary code rules identify different parts of the code base that are unnecessary and can be refactored or removed.</span></span> <span data-ttu-id="54560-105">불필요 한 코드가 있으면 다음 문제 중 하나를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54560-105">The presence of unnecessary code indicates one of more of the following problems:</span></span>

- <span data-ttu-id="54560-106">가독성: 가독성을 불필요 하 게 저하 하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="54560-106">Readability: Code that is unnecessarily degrading readability.</span></span> <span data-ttu-id="54560-107">예를 들어 [IDE0001](ide0001.md) 는 불필요 한 형식 이름 한정을 플래그 합니다.</span><span class="sxs-lookup"><span data-stu-id="54560-107">For example, [IDE0001](ide0001.md) flags unnecessary type-name qualifications.</span></span>
- <span data-ttu-id="54560-108">유지 관리: 리팩터링 후 더 이상 사용 되지 않고 불필요 하 게 유지 관리 되는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="54560-108">Maintainability: Code that is no longer used after refactoring and is unnecessarily being maintained.</span></span> <span data-ttu-id="54560-109">예를 들어, [IDE0051](ide0051.md) 는 사용 되지 않는 전용 필드, 속성, 이벤트 및 메서드에 플래그를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="54560-109">For example, [IDE0051](ide0051.md) flags unused private fields, properties, events, and methods.</span></span>
- <span data-ttu-id="54560-110">성능: 부작용이 없고 불필요 한 성능 오버 헤드를 초래 하는 불필요 한 계산입니다.</span><span class="sxs-lookup"><span data-stu-id="54560-110">Performance: Unnecessary computation that has no side effects and leads to unnecessary performance overhead.</span></span> <span data-ttu-id="54560-111">예를 들어, [IDE0059](ide0059.md) 는 값을 계산 하는 식에 파생 작업이 없는 경우 사용 하지 않는 값 할당 플래그를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54560-111">For example, [IDE0059](ide0059.md) flags unused value assignments where the expression to compute a value has no side effects.</span></span>
- <span data-ttu-id="54560-112">기능: 코드의 기능 문제로 인해 필요한 코드가 중복 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54560-112">Functionality: Functional issue in code leading to required code being rendered redundant.</span></span> <span data-ttu-id="54560-113">예를 들어, [IDE0060](ide0060.md) 는 메서드가 입력 매개 변수를 실수로 무시 하는 사용 되지 않는 매개 변수를 플래그 합니다.</span><span class="sxs-lookup"><span data-stu-id="54560-113">For example, [IDE0060](ide0060.md) flags unused parameters where the method accidentally ignores an input parameter.</span></span>

<span data-ttu-id="54560-114">이 단원의 규칙은 다음과 같은 불필요 한 코드 규칙을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="54560-114">The rules in this section concern the following unnecessary code rules:</span></span>

- [<span data-ttu-id="54560-115">이름 단순화 (IDE0001)</span><span class="sxs-lookup"><span data-stu-id="54560-115">Simplify name (IDE0001)</span></span>](ide0001.md)
- [<span data-ttu-id="54560-116">멤버 액세스 간소화 (IDE0002)</span><span class="sxs-lookup"><span data-stu-id="54560-116">Simplify member access (IDE0002)</span></span>](ide0002.md)
- [<span data-ttu-id="54560-117">불필요 한 캐스트 제거 (IDE0004)</span><span class="sxs-lookup"><span data-stu-id="54560-117">Remove unnecessary cast (IDE0004)</span></span>](ide0004.md)
- [<span data-ttu-id="54560-118">불필요 한 가져오기 제거 (IDE0005)</span><span class="sxs-lookup"><span data-stu-id="54560-118">Remove unnecessary import (IDE0005)</span></span>](ide0005.md)
- [<span data-ttu-id="54560-119">접근할 수 없는 코드 제거 (IDE0035)</span><span class="sxs-lookup"><span data-stu-id="54560-119">Remove unreachable code (IDE0035)</span></span>](ide0035.md)
- [<span data-ttu-id="54560-120">사용 하지 않는 전용 구성원 제거 (IDE0051)</span><span class="sxs-lookup"><span data-stu-id="54560-120">Remove unused private member (IDE0051)</span></span>](ide0051.md)
- [<span data-ttu-id="54560-121">읽지 않은 전용 구성원 제거 (IDE0052)</span><span class="sxs-lookup"><span data-stu-id="54560-121">Remove unread private member (IDE0052)</span></span>](ide0052.md)
- [<span data-ttu-id="54560-122">사용 하지 않는 식 값 제거 (IDE0058)</span><span class="sxs-lookup"><span data-stu-id="54560-122">Remove unused expression value (IDE0058)</span></span>](ide0058.md)
- [<span data-ttu-id="54560-123">불필요 한 값 할당 제거 (IDE0059)</span><span class="sxs-lookup"><span data-stu-id="54560-123">Remove unnecessary value assignment (IDE0059)</span></span>](ide0059.md)
- [<span data-ttu-id="54560-124">사용 하지 않는 매개 변수 제거 (IDE0060)</span><span class="sxs-lookup"><span data-stu-id="54560-124">Remove unused parameter (IDE0060)</span></span>](ide0060.md)
- [<span data-ttu-id="54560-125">불필요 한 비 표시 제거 (IDE0079)</span><span class="sxs-lookup"><span data-stu-id="54560-125">Remove unnecessary suppression (IDE0079)</span></span>](ide0079.md)
- <span data-ttu-id="54560-126">[불필요 한 비 표시 제거 연산자 (IDE0080)](ide0080.md) -c #에만 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="54560-126">[Remove unnecessary suppression operator (IDE0080)](ide0080.md) - C# only.</span></span>
- <span data-ttu-id="54560-127">[' ByVal ' (IDE0081)](ide0081.md) -Visual Basic만 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="54560-127">[Remove 'ByVal' (IDE0081)](ide0081.md) - Visual Basic only.</span></span>
- [<span data-ttu-id="54560-128">불필요 한 같음 연산자 제거 (IDE0100)</span><span class="sxs-lookup"><span data-stu-id="54560-128">Remove unnecessary equality operator (IDE0100)</span></span>](ide0100.md)
- <span data-ttu-id="54560-129">[불필요 한 삭제 (IDE0110)를 제거](ide0110.md) 합니다.-c #만 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="54560-129">[Remove unnecessary discard (IDE0110)](ide0110.md) - C# only.</span></span>

<span data-ttu-id="54560-130">이러한 규칙 중 일부에는 규칙 동작을 구성 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54560-130">Some of these rules have options to configure the rule behavior:</span></span>

- [<span data-ttu-id="54560-131">csharp_style_unused_value_expression_statement_preference (IDE0058)</span><span class="sxs-lookup"><span data-stu-id="54560-131">csharp_style_unused_value_expression_statement_preference (IDE0058)</span></span>](ide0058.md#csharp_style_unused_value_expression_statement_preference)
- [<span data-ttu-id="54560-132">visual_basic_style_unused_value_expression_statement_preference (IDE0058)</span><span class="sxs-lookup"><span data-stu-id="54560-132">visual_basic_style_unused_value_expression_statement_preference (IDE0058)</span></span>](ide0058.md#visual_basic_style_unused_value_expression_statement_preference)
- [<span data-ttu-id="54560-133">csharp_style_unused_value_assignment_preference (IDE0059)</span><span class="sxs-lookup"><span data-stu-id="54560-133">csharp_style_unused_value_assignment_preference (IDE0059)</span></span>](ide0059.md#csharp_style_unused_value_assignment_preference)
- [<span data-ttu-id="54560-134">visual_basic_style_unused_value_assignment_preference (IDE0059)</span><span class="sxs-lookup"><span data-stu-id="54560-134">visual_basic_style_unused_value_assignment_preference (IDE0059)</span></span>](ide0059.md#visual_basic_style_unused_value_assignment_preference)
- [<span data-ttu-id="54560-135">dotnet_code_quality_unused_parameters (IDE0060)</span><span class="sxs-lookup"><span data-stu-id="54560-135">dotnet_code_quality_unused_parameters (IDE0060)</span></span>](ide0060.md#dotnet_code_quality_unused_parameters)
- [<span data-ttu-id="54560-136">dotnet_remove_unnecessary_suppression_exclusions (IDE0079)</span><span class="sxs-lookup"><span data-stu-id="54560-136">dotnet_remove_unnecessary_suppression_exclusions (IDE0079)</span></span>](ide0079.md#dotnet_remove_unnecessary_suppression_exclusions)

## <a name="see-also"></a><span data-ttu-id="54560-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54560-137">See also</span></span>

- [<span data-ttu-id="54560-138">코드 스타일 언어 규칙</span><span class="sxs-lookup"><span data-stu-id="54560-138">Code style language rules</span></span>](language-rules.md)
- [<span data-ttu-id="54560-139">코드 스타일 규칙 참조</span><span class="sxs-lookup"><span data-stu-id="54560-139">Code style rules reference</span></span>](index.md)

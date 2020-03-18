---
title: 식별자 이름
description: C# 프로그래밍 언어에서 올바른 식별자 이름에 대한 규칙을 알아봅니다.
ms.date: 08/21/2018
ms.openlocfilehash: bef6e2ea285b5391af3350ae42a4105d140c6d1b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77673370"
---
# <a name="identifier-names"></a><span data-ttu-id="439d8-103">식별자 이름</span><span class="sxs-lookup"><span data-stu-id="439d8-103">Identifier names</span></span>

<span data-ttu-id="439d8-104">**식별자**는 형식(클래스, 인터페이스, 구조체, 대리자 또는 열거형), 멤버, 변수 또는 네임스페이스에 할당하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="439d8-104">An **identifier** is the name you assign to a type (class, interface, struct, delegate, or enum), member, variable, or namespace.</span></span> <span data-ttu-id="439d8-105">유효한 식별자는 다음 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="439d8-105">Valid identifiers must follow these rules:</span></span>

- <span data-ttu-id="439d8-106">식별자는 문자 또는 `_`로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="439d8-106">Identifiers must start with a letter, or `_`.</span></span>
- <span data-ttu-id="439d8-107">식별자에는 유니코드 문자, 10진수 문자, 유니코드 연결 문자, 유니코드 조합 문자 또는 유니코드 형식 문자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="439d8-107">Identifiers may contain Unicode letter characters, decimal digit characters, Unicode connecting characters, Unicode combining characters, or Unicode formatting characters.</span></span> <span data-ttu-id="439d8-108">유니코드 범주에 대한 자세한 내용은 [유니코드 범주 데이터베이스](https://www.unicode.org/reports/tr44/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="439d8-108">For more information on Unicode categories, see the [Unicode Category Database](https://www.unicode.org/reports/tr44/).</span></span>
<span data-ttu-id="439d8-109">식별자의 `@` 접두사를 사용하여 C# 키워드와 일치하는 식별자를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="439d8-109">You can declare identifiers that match C# keywords by using the `@` prefix on the identifier.</span></span> <span data-ttu-id="439d8-110">`@`는 식별자 이름의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="439d8-110">The `@` is not part of the identifier name.</span></span> <span data-ttu-id="439d8-111">예를 들어 `@if`는 `if`라는 식별자를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="439d8-111">For example, `@if` declares an identifier named `if`.</span></span> <span data-ttu-id="439d8-112">이러한 [verbatim 식별자](../../language-reference/tokens/verbatim.md)는 주로 다른 언어로 선언된 식별자와의 상호 운용성을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="439d8-112">These [verbatim identifiers](../../language-reference/tokens/verbatim.md) are primarily for interoperability with identifiers declared in other languages.</span></span>

<span data-ttu-id="439d8-113">유효한 식별자의 전체 정의는 [C# 언어 사양의 식별자 항목](../../../../_csharplang/spec/lexical-structure.md#identifiers)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="439d8-113">For a complete definition of valid identifiers, see the [Identifiers topic in the C# Language Specification](../../../../_csharplang/spec/lexical-structure.md#identifiers).</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="439d8-114">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="439d8-114">Naming conventions</span></span>

<span data-ttu-id="439d8-115">규칙 외에도 .NET API 전체에서 사용되는 여러 식별자 [명명 규칙](../../../standard/design-guidelines/naming-guidelines.md)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="439d8-115">In addition to the rules, there are a number of identifier [naming conventions](../../../standard/design-guidelines/naming-guidelines.md) used throughout the .NET APIs.</span></span> <span data-ttu-id="439d8-116">규칙에 따라 C# 프로그램은 형식 이름, 네임스페이스 및 모든 공용 멤버에 `PascalCase`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="439d8-116">By convention, C# programs use `PascalCase` for type names, namespaces, and all public members.</span></span> <span data-ttu-id="439d8-117">또한, 다음 규칙이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="439d8-117">In addition, the following conventions are common:</span></span>

- <span data-ttu-id="439d8-118">인터페이스 이름은 대문자 `I`로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="439d8-118">Interface names start with a capital `I`.</span></span>
- <span data-ttu-id="439d8-119">특성 유형은 `Attribute` 단어로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="439d8-119">Attribute types end with the word `Attribute`.</span></span>
- <span data-ttu-id="439d8-120">열거형 형식은 플래그가 아닌 경우에는 단수 명사를 사용하고 플래그인 경우에는 복수 명사를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="439d8-120">Enum types use a singular noun for non-flags, and a plural noun for flags.</span></span>
- <span data-ttu-id="439d8-121">식별자에는 두 개의 연속 `_` 문자가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="439d8-121">Identifiers should not contain two consecutive `_` characters.</span></span> <span data-ttu-id="439d8-122">이러한 이름은 컴파일러 생성 식별자용으로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="439d8-122">Those names are reserved for compiler generated identifiers.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="439d8-123">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="439d8-123">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="439d8-124">참조</span><span class="sxs-lookup"><span data-stu-id="439d8-124">See also</span></span>

- [<span data-ttu-id="439d8-125">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="439d8-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="439d8-126">C# 프로그램 내부</span><span class="sxs-lookup"><span data-stu-id="439d8-126">Inside a C# Program</span></span>](./index.md)
- [<span data-ttu-id="439d8-127">C# 참조</span><span class="sxs-lookup"><span data-stu-id="439d8-127">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="439d8-128">클래스</span><span class="sxs-lookup"><span data-stu-id="439d8-128">Classes</span></span>](../classes-and-structs/classes.md)
- [<span data-ttu-id="439d8-129">구조체 형식</span><span class="sxs-lookup"><span data-stu-id="439d8-129">Structure types</span></span>](../../language-reference/builtin-types/struct.md)
- [<span data-ttu-id="439d8-130">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="439d8-130">Namespaces</span></span>](../namespaces/index.md)
- [<span data-ttu-id="439d8-131">인터페이스</span><span class="sxs-lookup"><span data-stu-id="439d8-131">Interfaces</span></span>](../interfaces/index.md)
- [<span data-ttu-id="439d8-132">대리자</span><span class="sxs-lookup"><span data-stu-id="439d8-132">Delegates</span></span>](../delegates/index.md)

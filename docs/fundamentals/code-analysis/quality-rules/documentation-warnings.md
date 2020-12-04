---
title: 설명서 규칙 (코드 분석)
description: 코드 분석 규칙 문서 규칙에 대해 알아보기
ms.date: 09/16/2019
ms.topic: reference
f1_keywords:
- vs.codeanalysis.documentationrules
helpviewer_keywords:
- documentation rules
- managed code analysis rules, documentation rules
- warnings, documentation
author: mavasani
ms.author: mavasani
ms.openlocfilehash: 29d1734eec29bd00d456b4b00c48c2e8ef223441
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "96592664"
---
# <a name="documentation-rules"></a><span data-ttu-id="d7f8a-103">설명서 규칙</span><span class="sxs-lookup"><span data-stu-id="d7f8a-103">Documentation rules</span></span>

<span data-ttu-id="d7f8a-104">설명서 규칙은 외부에서 볼 수 있는 Api에 대 한 [XML 문서 주석을](../../../csharp/codedoc.md) 올바르게 사용 하 여 잘 문서화 된 라이브러리 작성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f8a-104">Documentation rules support writing well-documented libraries through the correct use of [XML documentation comments](../../../csharp/codedoc.md) for externally visible APIs.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d7f8a-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d7f8a-105">In this section</span></span>

| <span data-ttu-id="d7f8a-106">규칙</span><span class="sxs-lookup"><span data-stu-id="d7f8a-106">Rule</span></span> | <span data-ttu-id="d7f8a-107">설명</span><span class="sxs-lookup"><span data-stu-id="d7f8a-107">Description</span></span> |
| - | - |
| [<span data-ttu-id="d7f8a-108">CA1200: 접두사를 사용하여 cref 태그 사용 방지</span><span class="sxs-lookup"><span data-stu-id="d7f8a-108">CA1200: Avoid using cref tags with a prefix</span></span>](ca1200.md) | <span data-ttu-id="d7f8a-109">XML 문서 태그의 [cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) 특성은 "코드 참조"를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f8a-109">The [cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) attribute in an XML documentation tag means "code reference".</span></span> <span data-ttu-id="d7f8a-110">태그의 내부 텍스트를 형식, 메서드, 속성 등의 코드 요소로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f8a-110">It specifies that the inner text of the tag is a code element, such as a type, method, or property.</span></span> <span data-ttu-id="d7f8a-111">`cref`컴파일러가 참조를 확인 하는 것을 방지 하므로 접두사와 함께 태그를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="d7f8a-111">Avoid using `cref` tags with prefixes, because it prevents the compiler from verifying references.</span></span> <span data-ttu-id="d7f8a-112">또한 Visual Studio IDE (통합 개발 환경)에서 리팩터링 중에 이러한 기호 참조를 찾아 업데이트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f8a-112">It also prevents the Visual Studio integrated development environment (IDE) from finding and updating these symbol references during refactorings.</span></span> |

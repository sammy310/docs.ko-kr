---
title: XAML의 xml:space 처리
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 886f906b6d1e3a10920dbf52e36bf76324c5a9f2
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432703"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="a3501-102">XAML의 xml:space 처리</span><span class="sxs-lookup"><span data-stu-id="a3501-102">xml:space Handling in XAML</span></span>

<span data-ttu-id="a3501-103">특성은 `xml:space` 개체 요소 내에서 중요한 공백 처리 동작을 선언하는 XML 정의 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a3501-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="a3501-104">이 동작은 선언된 `xml:space` 요소 내에 포함된 모든 콘텐츠(내부 텍스트)와 관련이 있으며 자식 요소의 범위도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3501-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="a3501-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="a3501-105">XAML Attribute Usage</span></span>

```xaml
<object xml:space="preserve" />
```

 <span data-ttu-id="a3501-106">\- 또는-</span><span class="sxs-lookup"><span data-stu-id="a3501-106">\- or -</span></span>

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a><span data-ttu-id="a3501-107">설명</span><span class="sxs-lookup"><span data-stu-id="a3501-107">Remarks</span></span>

<span data-ttu-id="a3501-108">두 가지 `xml:space` 가능한 값을 포함하여 XAML의 특성에 `xml:space` 대한 정의는 XML에 대한 W3C 사양에 의해 "특수 특성"으로 정의된 대로 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3501-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>

<span data-ttu-id="a3501-109">`xml:space` 특성의 기본값은 리터럴 값입니다. `"default"`</span><span class="sxs-lookup"><span data-stu-id="a3501-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="a3501-110">값의 `"default"`경우 또는 `xml:space` 전혀 표시되지 않는 경우 [XAML의 공백 처리](white-space-processing.md)항목에 정의된 대로 중요한 공백 구문 분석의 동작이 기본 처리입니다.</span><span class="sxs-lookup"><span data-stu-id="a3501-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](white-space-processing.md).</span></span>

<span data-ttu-id="a3501-111">개체 요소 콘텐츠 내에서 공백을 `xml:space="preserve"` 유지하려면 해당 오브젝트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3501-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>

<span data-ttu-id="a3501-112">대부분의 해석에서 `xml:space` 특성 효과와 특성값은 자식 요소로 범위가 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3501-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>

<span data-ttu-id="a3501-113">XAML의 공백 처리에 대한 자세한 내용은 [XAML의 공백 처리를](white-space-processing.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a3501-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](white-space-processing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a3501-114">참조</span><span class="sxs-lookup"><span data-stu-id="a3501-114">See also</span></span>

- [<span data-ttu-id="a3501-115">XAML의 공백 처리</span><span class="sxs-lookup"><span data-stu-id="a3501-115">White-space processing in XAML</span></span>](white-space-processing.md)
- [<span data-ttu-id="a3501-116">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="a3501-116">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)

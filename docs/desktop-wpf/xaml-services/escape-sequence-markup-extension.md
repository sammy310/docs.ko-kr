---
title: '{}이스케이프 시퀀스 - 마크업 확장'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: f84243994557d76fa52d72b060a1ba35460e98b0
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432967"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="2a75b-102">{}이스케이프 시퀀스/마크업 확장</span><span class="sxs-lookup"><span data-stu-id="2a75b-102">{} Escape sequence / markup extension</span></span>

<span data-ttu-id="2a75b-103">특성 값에 대한 XAML 이스케이프 시퀀스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="2a75b-104">이스케이프 시퀀스를 사용하면 특성의 후속 값을 리터럴로 해석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="2a75b-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="2a75b-105">XAML Attribute Usage</span></span>

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a><span data-ttu-id="2a75b-106">XAML 속성 요소 사용</span><span class="sxs-lookup"><span data-stu-id="2a75b-106">XAML Property Element Usage</span></span>

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="2a75b-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="2a75b-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="2a75b-108">*리터럴 밸류값*</span><span class="sxs-lookup"><span data-stu-id="2a75b-108">*literalValue*</span></span>|<span data-ttu-id="2a75b-109">이스케이프 시퀀스를 따르는 리터럴 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="2a75b-110">일반적으로 이 문자열에는 열려 있거나 가까운 중괄호({ 또는 })가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-110">Typically this string contains an open or close brace ({ or }).</span></span>|

## <a name="remarks"></a><span data-ttu-id="2a75b-111">설명</span><span class="sxs-lookup"><span data-stu-id="2a75b-111">Remarks</span></span>

<span data-ttu-id="2a75b-112">이스케이프{}시퀀스 ()는 열린 중괄호({)를 XAML에서 리터럴 문자로 사용할 수 있도록 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-112">The escape sequence ({}) is used so that an open brace ({) can be used as a literal character in XAML.</span></span>

<span data-ttu-id="2a75b-113">XAML 판독기는 일반적으로 열린 중괄호({)를 사용하여 태그 확장의 진입점을 나타내지만 먼저 다음 문자를 확인하여 닫는 중괄호(})인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="2a75b-114">두 중괄호()가{}인접한 경우에만 이스케이프 시퀀스로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>

<span data-ttu-id="2a75b-115">이스케이프 시퀀스가 발생하면 XAML 판독기는 문자열의 나머지 부분을 문자열로 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="2a75b-116">그러나 이스케이프 시퀀스가 형식 변환기가 있는 멤버에 적용된 경우 XAML 작성자가 해석할 때 문자열이 형식 변환을 거칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>

<span data-ttu-id="2a75b-117">이스케이프 시퀀스는 태그 확장이 아니며 클래스에서 백업되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="2a75b-118">그러나 XAML 판독기(사용자 지정 XAML 판독기 포함)를 준수해야 하는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>

<span data-ttu-id="2a75b-119">따옴표(")는 이러한 방식으로 이스케이프 시퀀스로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="2a75b-120">비콘텐츠 속성에 대한 속성 값으로 따옴표를 설정해야 하는 경우 속성 요소 구문을 사용하고 따옴표를 속성 요소 내부에 문자열로 배치하거나 XML 문자 엔터티를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="2a75b-121">콘텐츠 속성의 경우 따옴표는 전체 콘텐츠일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-121">For a content property, the quotation mark can be the entire content.</span></span>

<span data-ttu-id="2a75b-122">이스케이프{}시퀀스 () 는 XAML 태그 확장이 나타날 수 있는 위치에 네임스페이스 한정자를 포함해야 하는 XML 형식을 지정할 때 자주 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="2a75b-123">이 위치에는 XAML 특성 값의 시작과 등호(=) 직후의 태그 확장이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-123">This location includes the start of a XAML attribute value, and in a markup extension immediately after an equal sign (=).</span></span> <span data-ttu-id="2a75b-124">다음 예제에서는 XAML 특성 값의 시작 부분에 나타나는 XML 네임스페이스에 대한 이스케이프 시퀀스를 보여 주며, 이스케이프 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="2a75b-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a><span data-ttu-id="2a75b-125">참조</span><span class="sxs-lookup"><span data-stu-id="2a75b-125">See also</span></span>

- [<span data-ttu-id="2a75b-126">XAML을 위한 형식 변환기 및 태그 확장</span><span class="sxs-lookup"><span data-stu-id="2a75b-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions.md)
- [<span data-ttu-id="2a75b-127">XML 문자 엔터티 및 XAML</span><span class="sxs-lookup"><span data-stu-id="2a75b-127">XML Character Entities and XAML</span></span>](xml-character-entities.md)

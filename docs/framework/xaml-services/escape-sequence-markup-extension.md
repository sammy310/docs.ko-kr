---
title: '{}이스케이프 시퀀스 태그 확장'
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
ms.openlocfilehash: b0646c62a1342eb160d1967e86ac286429013f3c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053869"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="ae938-102">{} 이스케이프 시퀀스/태그 확장명</span><span class="sxs-lookup"><span data-stu-id="ae938-102">{} Escape Sequence / Markup Extension</span></span>
<span data-ttu-id="ae938-103">특성 값에 대 한 XAML 이스케이프 시퀀스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae938-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="ae938-104">이스케이프 시퀀스를 사용 하면 특성의 후속 값이 리터럴로 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae938-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="ae938-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="ae938-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="ae938-106">XAML 속성 요소 사용</span><span class="sxs-lookup"><span data-stu-id="ae938-106">XAML Property Element Usage</span></span>  
  
```xaml  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="ae938-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="ae938-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ae938-108">*literalValue*</span><span class="sxs-lookup"><span data-stu-id="ae938-108">*literalValue*</span></span>|<span data-ttu-id="ae938-109">이스케이프 시퀀스 뒤에 오는 리터럴 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ae938-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="ae938-110">일반적으로이 문자열에는 여는 중괄호 ({또는})가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae938-110">Typically this string contains an open or close brace ({ or }).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae938-111">설명</span><span class="sxs-lookup"><span data-stu-id="ae938-111">Remarks</span></span>  
 <span data-ttu-id="ae938-112">이스케이프 시퀀스 ({})는 XAML에서 여는 중괄호 ({)를 리터럴 문자로 사용할 수 있도록 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae938-112">The escape sequence ({}) is used so that an open brace ({)can be used as a literal character in XAML.</span></span>  
  
 <span data-ttu-id="ae938-113">일반적으로 XAML 판독기는 여는 중괄호 ({)를 사용 하 여 태그 확장의 진입점을 나타냅니다. 그러나 먼저 다음 문자를 검사 하 여 닫는 중괄호 (}) 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae938-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="ae938-114">두 중괄호 ({})가 인접 한 경우에만 이스케이프 시퀀스로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae938-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>  
  
 <span data-ttu-id="ae938-115">이스케이프 시퀀스가 발생 하는 경우 XAML 판독기는 문자열의 나머지를 문자열로 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae938-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="ae938-116">그러나 이스케이프 시퀀스가 형식 변환기를 포함 하는 멤버에 적용 되는 경우에는 XAML 작성기에서 해석 될 때 문자열을 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae938-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>  
  
 <span data-ttu-id="ae938-117">이스케이프 시퀀스가 태그 확장이 아니고 클래스에서 지원 되지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="ae938-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="ae938-118">그러나이는 XAML 판독기 (사용자 지정 XAML 판독기 포함)가 따라야 하는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="ae938-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>  
  
 <span data-ttu-id="ae938-119">이 방식에서는 따옴표 (")를 이스케이프 시퀀스로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae938-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="ae938-120">콘텐츠가 아닌 속성의 속성 값으로 따옴표를 설정 해야 하는 경우 속성 요소 구문을 사용 하 고 따옴표를 속성 요소 내에 문자열로 삽입 하거나 XML 문자 엔터티를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae938-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="ae938-121">콘텐츠 속성의 경우 인용 부호는 전체 콘텐츠가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae938-121">For a content property, the quotation mark can be the entire content.</span></span>  
  
 <span data-ttu-id="ae938-122">이스케이프 시퀀스 ({})는 XAML 태그 확장이 나타날 수 있는 위치에 네임 스페이스 한정자를 포함 해야 하는 XML 형식을 지정할 때 자주 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae938-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="ae938-123">여기에는 XAML 특성 값의 시작과 태그 확장의 등호 (=) 바로 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae938-123">This includes the start of a XAML attribute value, and in a markup extension, immediately after an equal sign (=).</span></span> <span data-ttu-id="ae938-124">다음 예제에서는 XAML 특성 값의 시작 부분에 표시 되는 XML 네임 스페이스에 대 한 이스케이프 시퀀스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae938-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>  
  
 [!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a><span data-ttu-id="ae938-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="ae938-125">See also</span></span>

- [<span data-ttu-id="ae938-126">XAML을 위한 형식 변환기 및 태그 확장명</span><span class="sxs-lookup"><span data-stu-id="ae938-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions-for-xaml.md)
- [<span data-ttu-id="ae938-127">XML 문자 엔터티 및 XAML</span><span class="sxs-lookup"><span data-stu-id="ae938-127">XML Character Entities and XAML</span></span>](xml-character-entities-and-xaml.md)

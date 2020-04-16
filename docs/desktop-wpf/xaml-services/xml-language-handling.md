---
title: XAML의 xml:lang 처리
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
ms.openlocfilehash: b5a06adbb7cb874bc09899118f13b91fbec7a85e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432709"
---
# <a name="xmllang-handling-in-xaml"></a><span data-ttu-id="7edc6-102">XAML의 xml:lang 처리</span><span class="sxs-lookup"><span data-stu-id="7edc6-102">xml:lang Handling in XAML</span></span>

<span data-ttu-id="7edc6-103">특성은 `xml:lang` XML의 요소에 대한 언어 및 문화문화 정보를 선언하는 XML 정의 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7edc6-103">The `xml:lang` attribute is an XML-defined attribute that declares the language and culture information for an element in XML.</span></span> <span data-ttu-id="7edc6-104">XAML을 사용해도 특성의 의미가 동일하게 유지되지만, 일부 추가적인 고려 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7edc6-104">This same meaning of the attribute persists in XAML; however, some additional considerations apply.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="7edc6-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="7edc6-105">XAML Attribute Usage</span></span>

```xaml
<object xml:lang="rfc3066lang" />
```

## <a name="xaml-values"></a><span data-ttu-id="7edc6-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="7edc6-106">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="7edc6-107">*rfc3066lang*</span><span class="sxs-lookup"><span data-stu-id="7edc6-107">*rfc3066lang*</span></span>|<span data-ttu-id="7edc6-108">[RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) 표준에서 파생되고 언어 또는 언어 영역을 식별하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7edc6-108">A string that is derived from the [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) standard and identifies either a language or a language-region.</span></span> <span data-ttu-id="7edc6-109">후자의 경우, 언어 및 지역이 단일 하이픈으로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="7edc6-109">When it is the latter, the language and region are separated by a single hyphen.</span></span> <span data-ttu-id="7edc6-110">값 및 형식에 대한 자세한 내용은 <xref:System.Windows.Markup.XmlLanguage> 를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7edc6-110">See <xref:System.Windows.Markup.XmlLanguage> for more information about the values and format.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7edc6-111">설명</span><span class="sxs-lookup"><span data-stu-id="7edc6-111">Remarks</span></span>

<span data-ttu-id="7edc6-112">속성에 `xml:lang` 대한 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 정의는 XML에 `xml:lang` 대한 W3C(월드 와이드 웹 컨소시엄)에서 "특수 특성"으로 정의된 것으로부터 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="7edc6-112">The definition for the `xml:lang` attribute in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] is derived from `xml:lang` as defined as a "special attribute" by the World Wide Web Consortium (W3C) for XML.</span></span> <span data-ttu-id="7edc6-113">언어 및 문화권 정보는 구현에 따라 요소에서 다양한 방법으로 처리될 수 있습니다. 하지만 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 특성의 기본 `xml:lang` 처리는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7edc6-113">Language and culture information is potentially processed in different ways by elements, depending on their implementations; however, there is no default [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing of the `xml:lang` attribute.</span></span>

<span data-ttu-id="7edc6-114">`xml:lang` 특성의 기본값은 이 특성 수준의 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7edc6-114">The default value of the `xml:lang` attribute is an empty string at the attribute level.</span></span>

<span data-ttu-id="7edc6-115">`xml:lang` 특성 효과 및 특성의 값은 일반적으로 `xml:lang` 값에 영향을 주는 시스템에서 해석될 때 자식 요소에 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="7edc6-115">The `xml:lang` attribute effects and the value of the attribute are generally perpetuated to child elements, when interpreted by systems that act on `xml:lang` values.</span></span>

<span data-ttu-id="7edc6-116">.NET XAML 서비스의 XAML 작성자가 `xml:lang` 해석할 <xref:System.Windows.Markup.XmlLanguage> 때 <xref:System.Globalization.CultureInfo> 값은 기본 개체 표현에서 만들거나 개체를 만들 수 있습니다. 그러나 해당 동작은 지정된 `xml:lang` 값이 해당 클래스에 대한 유효한 구성인지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="7edc6-116">When interpreted by XAML writers of .NET XAML Services, an `xml:lang` value can create <xref:System.Windows.Markup.XmlLanguage> or <xref:System.Globalization.CultureInfo> objects in the underlying object representation; however, that behavior depends on whether the value specified for `xml:lang` is a valid construction for those classes.</span></span>

<span data-ttu-id="7edc6-117">프레임워크는 `xml:lang` 를 속성에 적용하여 프레임워크에서 정의된 속성과 <xref:System.Windows.Markup.XmlLangPropertyAttribute> 의 의미 사이에 연결을 XML 형식으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7edc6-117">Frameworks can create associations between framework-defined properties and the meaning of `xml:lang` in XML by applying <xref:System.Windows.Markup.XmlLangPropertyAttribute> to the property.</span></span>

## <a name="wpf-usage-nodes"></a><span data-ttu-id="7edc6-118">WPF 사용 노드</span><span class="sxs-lookup"><span data-stu-id="7edc6-118">WPF Usage Nodes</span></span>

<span data-ttu-id="7edc6-119"><xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>의 파생 클래스인 요소의 경우, <xref:System.Windows.FrameworkElement.Language%2A> 특성의 해당되는 `xml:lang` 종속성 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7edc6-119">For elements that are derived classes of <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement>, you can use the equivalent <xref:System.Windows.FrameworkElement.Language%2A> dependency property instead of the `xml:lang` attribute.</span></span> <span data-ttu-id="7edc6-120">기본적으로, <xref:System.Windows.FrameworkElement.Language%2A> 속성은 이 속성 또는 `xml:lang` 특성 처리를 통해 달리 설정되지 않은 경우 "en-US"를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7edc6-120">By default, the <xref:System.Windows.FrameworkElement.Language%2A> property uses "en-US" if it is not otherwise set, either through the property or through processing the `xml:lang` attribute.</span></span>

## <a name="see-also"></a><span data-ttu-id="7edc6-121">참조</span><span class="sxs-lookup"><span data-stu-id="7edc6-121">See also</span></span>

- [<span data-ttu-id="7edc6-122">WPF의 전역화</span><span class="sxs-lookup"><span data-stu-id="7edc6-122">Globalization for WPF</span></span>](../../framework/wpf/advanced/globalization-for-wpf.md)

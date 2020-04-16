---
title: x:Reference 태그 확장
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: f06e259893111a436e5afe2df754c3edee326d54
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432655"
---
# <a name="xreference-markup-extension"></a><span data-ttu-id="d1e0a-102">x:Reference 태그 확장</span><span class="sxs-lookup"><span data-stu-id="d1e0a-102">x:Reference Markup Extension</span></span>

<span data-ttu-id="d1e0a-103">XAML 태그의 다른 위치에 선언된 인스턴스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0a-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="d1e0a-104">참조는 요소의 을 `x:Name`참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0a-104">The reference refers to an element's `x:Name`.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="d1e0a-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="d1e0a-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Reference instancexName}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="d1e0a-106">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="d1e0a-106">XAML Object Element Usage</span></span>

```xaml
<object>
  <object.property>
    <x:Reference Name="instancexName"/>
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="d1e0a-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="d1e0a-107">XAML Values</span></span>

|||
|-|-|
|`instancexName`|<span data-ttu-id="d1e0a-108">참조된 인스턴스의 `x:Name` 값(또는 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified 속성의 값)입니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0a-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d1e0a-109">설명</span><span class="sxs-lookup"><span data-stu-id="d1e0a-109">Remarks</span></span>

<span data-ttu-id="d1e0a-110">`x:Reference`는 WPF와 같은 특정 프레임워크에서 구현된 요소 참조 개념에 대한 XAML 언어 수준 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0a-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>

## <a name="xreference-and-wpf"></a><span data-ttu-id="d1e0a-111">x:참조 및 WPF</span><span class="sxs-lookup"><span data-stu-id="d1e0a-111">x:Reference and WPF</span></span>

<span data-ttu-id="d1e0a-112">WPF 및 XAML 2006에서 요소 참조는 바인딩의 <xref:System.Windows.Data.Binding.ElementName%2A> 프레임워크 수준 기능에 의해 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0a-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="d1e0a-113">대부분의 WPF 응용 프로그램 <xref:System.Windows.Data.Binding.ElementName%2A> 및 시나리오에서 바인딩은 계속 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0a-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="d1e0a-114">이 일반 지침의 예외에는 데이터 바인딩을 비실용적으로 만드는 데이터 컨텍스트 또는 기타 범위 지정 고려 사항이 있는 경우와 태그 컴파일이 포함되지 않은 경우가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0a-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>

<span data-ttu-id="d1e0a-115">`x:Reference`는 XAML 2009에 정의된 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0a-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="d1e0a-116">WPF에서 XAML 2009 기능을 사용할 수 있지만 WPF 태그 컴파일된 XAML에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0a-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="d1e0a-117">태그 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 언어 키워드 및 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0a-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>

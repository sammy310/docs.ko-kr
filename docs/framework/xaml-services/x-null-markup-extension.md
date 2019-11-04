---
title: x:Null 태그 확장명
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: ff82b0bfc1983240431e582dbd78778dc4469241
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459939"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="604b5-102">x:Null 태그 확장명</span><span class="sxs-lookup"><span data-stu-id="604b5-102">x:Null Markup Extension</span></span>
<span data-ttu-id="604b5-103">`null`를 XAML 멤버에 대 한 값으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="604b5-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="604b5-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="604b5-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="604b5-105">주의</span><span class="sxs-lookup"><span data-stu-id="604b5-105">Remarks</span></span>  
 <span data-ttu-id="604b5-106">및 C# C++ 의 null 참조에 대 한 키워드가 null 인 경우</span><span class="sxs-lookup"><span data-stu-id="604b5-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="604b5-107">Null 참조에 대 한 Microsoft Visual Basic 키워드는 `Nothing`있지만 XAML과 연결 하는 코드 기반 언어에 관계 없이 항상 `{x:Null}`를 XAML 사용으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="604b5-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="604b5-108">`x:Null` 태그 확장에 설정 가능한 속성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="604b5-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="604b5-109">Null 사용은 종종 CLR <xref:System.Nullable%601> 값의 XAML 멤버 노출에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="604b5-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="604b5-110">모든 XAML 태그 확장과 마찬가지로 `x:Null` 태그 확장은 중괄호 (`{,}`)를 사용 하 여 특성 값의 처리를 리터럴 또는 이벤트 처리기 참조 이외의 값으로 이스케이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="604b5-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="604b5-111">특성 구문은이 태그 확장에서 가장 자주 사용 되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="604b5-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="604b5-112">`<x:Null />` 개체 요소 구문이 기술적으로 가능 하지만 `x:Null` 태그 확장에 위치 매개 변수 또는 생성 인수가 없기 때문에 거의 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="604b5-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="604b5-113">태그 확장에 대 한 자세한 내용은 [태그 확장 및 WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="604b5-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="604b5-114">.NET Framework XAML 서비스에서이 태그 확장에 대 한 처리는 <xref:System.Windows.Markup.NullExtension> 클래스에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="604b5-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="604b5-115">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="604b5-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="604b5-116">참조 형식 종속성 속성에 대 한 초기 설정 되지 않은 값이 반드시 `null`은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="604b5-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="604b5-117">초기 기본값은 각 종속성 속성에 따라 다를 수 있으며 속성 관련 메타 데이터를 기반으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604b5-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="604b5-118">많은 종속성 속성은 유효성 검사 콜백 구현 때문에 태그 또는 코드를 통해 `null`을 값으로 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="604b5-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="604b5-119">종속성 속성에 대 한 자세한 내용은 [종속성 속성 개요](../wpf/advanced/dependency-properties-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="604b5-119">For more information about dependency properties, see [Dependency Properties Overview](../wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604b5-120">참조</span><span class="sxs-lookup"><span data-stu-id="604b5-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="604b5-121">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="604b5-121">XAML Overview (WPF)</span></span>](../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="604b5-122">태그 확장 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="604b5-122">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)

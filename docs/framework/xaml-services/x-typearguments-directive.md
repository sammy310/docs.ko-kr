---
title: x:TypeArguments 지시문
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 1d1b10b4da1263843bdce5447f0716569c7700e3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085807"
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="08b59-102">x:TypeArguments 지시문</span><span class="sxs-lookup"><span data-stu-id="08b59-102">x:TypeArguments Directive</span></span>
<span data-ttu-id="08b59-103">전달 된 제네릭 형식의 생성자에 제네릭 인수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="08b59-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="08b59-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="08b59-105">XAML 값</span><span class="sxs-lookup"><span data-stu-id="08b59-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`object`|<span data-ttu-id="08b59-106">CLR 제네릭 형식에서 지원 되는 XAML 형식의 개체 요소 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="08b59-107">하는 경우 `object` 아니라 기본 XAML 네임 스페이스는 XAML 형식을 참조 `object` 나타내는 XAML 네임 스페이스 접두사가 필요 여기서 `object` 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|  
|`typeString`|<span data-ttu-id="08b59-108">하나 이상의 XAML을 선언 하는 문자열에 입력 문자열로 CLR 제네릭 형식의 형식 인수를 제공 하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="08b59-109">자세한 구문 정보에 대 한 설명을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="08b59-109">See Remarks for additional syntax notes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08b59-110">설명</span><span class="sxs-lookup"><span data-stu-id="08b59-110">Remarks</span></span>  
 <span data-ttu-id="08b59-111">대부분의 경우에서 정보 항목으로 사용 되는 XAML 형식에는 `typeString` 문자열 붙습니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="08b59-112">일반적인 유형의 CLR 제네릭 제약 조건 (예를 들어 <xref:System.Int32> 고 <xref:System.String>) CLR 기본 클래스 라이브러리에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="08b59-113">해당 라이브러리에 일반적인 매핑된 프레임 워크 관련 기본 XAML 네임 스페이스에 없는 및 따라서 접두사 매핑을 XAML 사용에 대 한 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>  
  
 <span data-ttu-id="08b59-114">쉼표 구분 기호를 사용 하 여 둘 이상의 XAML 형식 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>  
  
 <span data-ttu-id="08b59-115">제네릭 제약 조건 자체가 제네릭 형식을 사용 하는 경우 중첩 된 제약 조건 형식 인수는 괄호 () 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>  
  
 <span data-ttu-id="08b59-116">이 정의의 `x:TypeArguments` .NET Framework XAML 서비스와 관련 되 고 CLR 백업의 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-116">Note that this definition of `x:TypeArguments` is specific to .NET Framework XAML Services and using CLR backing.</span></span> <span data-ttu-id="08b59-117">언어 수준 정의에서 찾을 수 있습니다 [ \[MS XAML\] 5.3.11 섹션](https://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="usage-examples"></a><span data-ttu-id="08b59-118">사용 예제</span><span class="sxs-lookup"><span data-stu-id="08b59-118">Usage Examples</span></span>  
 <span data-ttu-id="08b59-119">이러한 예를 들어 다음 XAML 네임 스페이스 정의 선언 된 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a><span data-ttu-id="08b59-120">목록\<문자열 ></span><span class="sxs-lookup"><span data-stu-id="08b59-120">List\<String></span></span>  
 `<scg:List x:TypeArguments="sys:String" ...>` <span data-ttu-id="08b59-121">새 인스턴스화합니다 <xref:System.Collections.Generic.List%601> 사용 하 여는 <xref:System.String> 인수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-121">instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>  
  
### <a name="dictionarystringstring"></a><span data-ttu-id="08b59-122">사전\<문자열, 문자열 ></span><span class="sxs-lookup"><span data-stu-id="08b59-122">Dictionary\<String,String></span></span>  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` <span data-ttu-id="08b59-123">새 인스턴스화합니다 <xref:System.Collections.Generic.Dictionary%602> 두 개의 <xref:System.String> 인수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-123">instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>  
  
### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="08b59-124">Queue<KeyValuePair\<String,String>></span><span class="sxs-lookup"><span data-stu-id="08b59-124">Queue<KeyValuePair\<String,String>></span></span>  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` <span data-ttu-id="08b59-125">새 인스턴스화합니다 <xref:System.Collections.Generic.Queue%601> 의 제약 조건이 있는 <xref:System.Collections.Generic.KeyValuePair%602> 내부 제약 조건 형식 인수를 사용 하 여 <xref:System.String> 고 <xref:System.String>입니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-125">instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="08b59-126">XAML 2006 및 WPF 일반 XAML 사용</span><span class="sxs-lookup"><span data-stu-id="08b59-126">XAML 2006 and WPF Generic XAML Usages</span></span>  
 <span data-ttu-id="08b59-127">XAML 2006 사용 및 WPF 응용 프로그램에 사용 되는 XAML의 경우는 다음과 같은 제한 사항이 `x:TypeArguments` 및 일반 XAML에서 제네릭 형식 사용:</span><span class="sxs-lookup"><span data-stu-id="08b59-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>  
  
-   <span data-ttu-id="08b59-128">XAML 파일의 루트 요소에만 제네릭 형식을 참조 하는 제네릭 XAML 사용을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>  
  
-   <span data-ttu-id="08b59-129">루트 요소는 하나 이상의 형식 인수가 있는 제네릭 형식에 매핑되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="08b59-130">예로 <xref:System.Windows.Navigation.PageFunction%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="08b59-131">페이지는 WPF의 XAML 제네릭 사용 지원에 대 한 기본 시나리오.</span><span class="sxs-lookup"><span data-stu-id="08b59-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>  
  
-   <span data-ttu-id="08b59-132">제네릭에 대 한 루트 요소 XAML 개체 요소를 사용 하 여 partial 클래스를 선언 해야 합니다 `x:Class`합니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="08b59-133">빌드 작업 WPF를 정의 하는 경우에 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-133">This is true even if defining a WPF build action.</span></span>  
  
-   `x:TypeArguments` <span data-ttu-id="08b59-134">중첩 된 제네릭 제약을 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-134">cannot reference nested generic constraints.</span></span>  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="08b59-135">XAML 2009 또는 WPF 3.0 또는 3.5 WPF 없이 XAML 2006 종속성</span><span class="sxs-lookup"><span data-stu-id="08b59-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>  
 <span data-ttu-id="08b59-136">XAML 2006 또는 XAML 2009에 대 한.NET Framework XAML 서비스에서 제네릭 XAML 사용에 WPF 관련 대 한 제한이 완화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-136">In .NET Framework XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="08b59-137">XAML 태그는 지원 형식 시스템 및 개체 모델을 지원할 수 있는 모든 위치에서 일반 개체 요소를 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>  
  
 <span data-ttu-id="08b59-138">XAML 2009를 사용 하는 경우 CLR 대신 기본 공용 언어 기본 형식에 대 한 XAML 형식을 가져올 형식, 사용할 수 있습니다 [공용 XAML 언어 기본 형식에 대 한 기본 제공 형식](built-in-types-for-common-xaml-language-primitives.md) 의 정보 항목으로는 `typeString`합니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](built-in-types-for-common-xaml-language-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="08b59-139">예를 들어, 다음에 선언할 수 있습니다 (접두사 매핑이 표시 되지 않지만 x는 XAML 2009에 대해 XAML 언어 XAML 네임 스페이스):</span><span class="sxs-lookup"><span data-stu-id="08b59-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 <span data-ttu-id="08b59-140">Wpf에서 및 대상으로 할 때 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]와 함께 XAML 2009 기능을 사용할 수 있습니다 `x:TypeArguments` 느슨한 XAML (태그 컴파일되지 않은 XAML)에 대해서만 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-140">In WPF and when targeting [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="08b59-141">WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="08b59-142">태그에는 XAML을 컴파일해야 하는 경우 "XAML 2006 및 WPF 일반 XAML 사용" 섹션에서 설명한 제한에서 작동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b59-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the "XAML 2006 and WPF Generic XAML Usages" section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08b59-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="08b59-143">See also</span></span>

- [<span data-ttu-id="08b59-144">x:Class 지시문</span><span class="sxs-lookup"><span data-stu-id="08b59-144">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="08b59-145">x:Type 태그 확장</span><span class="sxs-lookup"><span data-stu-id="08b59-145">x:Type Markup Extension</span></span>](x-type-markup-extension.md)
- [<span data-ttu-id="08b59-146">공용 XAML 언어 기본 형식에 대한 기본 제공 형식</span><span class="sxs-lookup"><span data-stu-id="08b59-146">Built-in Types for Common XAML Language Primitives</span></span>](built-in-types-for-common-xaml-language-primitives.md)
- [<span data-ttu-id="08b59-147">XAML의 제네릭</span><span class="sxs-lookup"><span data-stu-id="08b59-147">Generics in XAML</span></span>](generics-in-xaml.md)

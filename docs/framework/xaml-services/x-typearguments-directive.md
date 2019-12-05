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
ms.openlocfilehash: 2e64c716ee85934bf02c016ee408b8e5f612a819
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837196"
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="67b98-102">x:TypeArguments 지시문</span><span class="sxs-lookup"><span data-stu-id="67b98-102">x:TypeArguments Directive</span></span>
<span data-ttu-id="67b98-103">제네릭의 제약 조건 형식 인수를 제네릭 형식의 생성자에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="67b98-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="67b98-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="67b98-105">XAML 값</span><span class="sxs-lookup"><span data-stu-id="67b98-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`object`|<span data-ttu-id="67b98-106">CLR 제네릭 형식에 의해 지원 되는 XAML 형식의 개체 요소 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="67b98-107">`object` 기본 XAML 네임 스페이스에 없는 XAML 형식을 참조 하는 경우 `object`에 `object` 있는 XAML 네임 스페이스를 나타내는 접두사가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|  
|`typeString`|<span data-ttu-id="67b98-108">하나 이상의 XAML 형식 이름을 문자열로 선언 하는 문자열로, CLR 제네릭 형식에 대 한 형식 인수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="67b98-109">추가 구문 정보는 설명 부분을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="67b98-109">See Remarks for additional syntax notes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67b98-110">주의</span><span class="sxs-lookup"><span data-stu-id="67b98-110">Remarks</span></span>  
 <span data-ttu-id="67b98-111">대부분의 경우 `typeString` 문자열에서 정보 항목으로 사용 되는 XAML 형식에는 접두사가 붙습니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="67b98-112">Clr 기본 클래스 라이브러리에서 일반적인 형식의 CLR 제네릭 제약 조건 (예: <xref:System.Int32> 및 <xref:System.String>)이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="67b98-113">이러한 라이브러리는 일반적인 프레임 워크 특정 기본 XAML 네임 스페이스에 매핑되지 않으므로 XAML 사용을 위해 접두사 매핑이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>  
  
 <span data-ttu-id="67b98-114">쉼표 구분 기호를 사용 하 여 둘 이상의 XAML 형식 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>  
  
 <span data-ttu-id="67b98-115">제네릭 제약 조건 자체가 제네릭 형식을 사용 하는 경우 중첩 된 제약 조건 형식 인수는 괄호 ()에 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>  
  
 <span data-ttu-id="67b98-116">이 `x:TypeArguments` 정의는 .NET Framework XAML 서비스 및 CLR 지원 사용에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-116">Note that this definition of `x:TypeArguments` is specific to .NET Framework XAML Services and using CLR backing.</span></span> <span data-ttu-id="67b98-117">언어 수준 정의는 [\[MS-XAML\] 섹션 5.3.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>  
  
## <a name="usage-examples"></a><span data-ttu-id="67b98-118">사용 예제</span><span class="sxs-lookup"><span data-stu-id="67b98-118">Usage Examples</span></span>  
 <span data-ttu-id="67b98-119">이러한 예제에서는 다음 XAML 네임 스페이스 정의가 선언 된 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>  
  
```xaml  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a><span data-ttu-id="67b98-120">\<문자열을 나열 ></span><span class="sxs-lookup"><span data-stu-id="67b98-120">List\<String></span></span>  
 <span data-ttu-id="67b98-121">`<scg:List x:TypeArguments="sys:String" ...>` <xref:System.String> 형식 인수를 사용 하 여 새 <xref:System.Collections.Generic.List%601>를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>  
  
### <a name="dictionarystringstring"></a><span data-ttu-id="67b98-122">사전\<문자열, 문자열 ></span><span class="sxs-lookup"><span data-stu-id="67b98-122">Dictionary\<String,String></span></span>  
 <span data-ttu-id="67b98-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`는 두 개의 <xref:System.String> 형식 인수를 사용 하 여 새 <xref:System.Collections.Generic.Dictionary%602>를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>  
  
### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="67b98-124">큐 < KeyValuePair\<문자열, 문자열 > ></span><span class="sxs-lookup"><span data-stu-id="67b98-124">Queue<KeyValuePair\<String,String>></span></span>  
 <span data-ttu-id="67b98-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`는 <xref:System.String> 및 <xref:System.String>내부 제약 조건 형식 인수를 사용 하 여 <xref:System.Collections.Generic.KeyValuePair%602> 제약 조건이 있는 새 <xref:System.Collections.Generic.Queue%601>를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="67b98-126">XAML 2006 및 WPF 일반 XAML 사용</span><span class="sxs-lookup"><span data-stu-id="67b98-126">XAML 2006 and WPF Generic XAML Usages</span></span>  
 <span data-ttu-id="67b98-127">WPF 응용 프로그램에 사용 되는 xaml 2006 사용 및 XAML의 경우 일반적인 XAML의 `x:TypeArguments` 및 제네릭 형식 사용에는 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>  
  
- <span data-ttu-id="67b98-128">XAML 파일의 루트 요소만 제네릭 형식을 참조 하는 일반 XAML 사용을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>  
  
- <span data-ttu-id="67b98-129">루트 요소는 하나 이상의 형식 인수가 있는 제네릭 형식에 매핑되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="67b98-130">예제입니다. <xref:System.Windows.Navigation.PageFunction%601></span><span class="sxs-lookup"><span data-stu-id="67b98-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="67b98-131">페이지 함수는 WPF의 XAML 제네릭 사용 지원에 대 한 주요 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>  
  
- <span data-ttu-id="67b98-132">제네릭의 루트 요소 XAML 개체 요소는 또한 `x:Class`를 사용 하 여 partial 클래스를 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="67b98-133">WPF 빌드 작업을 정의 하는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-133">This is true even if defining a WPF build action.</span></span>  
  
- <span data-ttu-id="67b98-134">`x:TypeArguments`는 중첩 된 제네릭 제약 조건을 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="67b98-135">WPF 3.0 또는 WPF 3.5 종속성이 없는 XAML 2009 또는 XAML 2006</span><span class="sxs-lookup"><span data-stu-id="67b98-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>  
 <span data-ttu-id="67b98-136">Xaml 2006 또는 xaml 2009에 대 한 .NET Framework XAML 서비스에서는 제네릭 XAML 사용에 대 한 WPF 관련 제한이 완화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-136">In .NET Framework XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="67b98-137">지원 형식 시스템 및 개체 모델에서 지원할 수 있는 XAML 태그의 임의 위치에서 제네릭 개체 요소를 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>  
  
 <span data-ttu-id="67b98-138">CLR 기본 형식을 매핑하는 대신 XAML 2009를 사용 하 여 공용 언어 기본 형식의 XAML 형식을 가져오는 경우 [일반적인 Xaml 언어 기본 형식에 대 한 기본 제공 형식을](built-in-types-for-common-xaml-language-primitives.md) `typeString`의 정보 항목으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](built-in-types-for-common-xaml-language-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="67b98-139">예를 들어 다음을 선언할 수 있습니다 (접두사 매핑은 표시 되지 않지만 x는 XAML 2009에 대 한 XAML 언어 XAML 네임 스페이스).</span><span class="sxs-lookup"><span data-stu-id="67b98-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 <span data-ttu-id="67b98-140">WPF 및 .NET Framework 4를 대상으로 지정 하는 경우 XAML 2009 기능을 `x:TypeArguments`와 함께 사용할 수 있지만 느슨한 XAML (태그 컴파일되지 않은 XAML)에 대해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-140">In WPF and when targeting .NET Framework 4, you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="67b98-141">WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="67b98-142">XAML 태그를 표시 해야 하는 경우 "XAML 2006 및 WPF Generic XAML 사용" 섹션에 설명 된 제한에 따라 작업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67b98-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the "XAML 2006 and WPF Generic XAML Usages" section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67b98-143">참조</span><span class="sxs-lookup"><span data-stu-id="67b98-143">See also</span></span>

- [<span data-ttu-id="67b98-144">x:Class 지시문</span><span class="sxs-lookup"><span data-stu-id="67b98-144">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="67b98-145">x:Type 태그 확장</span><span class="sxs-lookup"><span data-stu-id="67b98-145">x:Type Markup Extension</span></span>](x-type-markup-extension.md)
- [<span data-ttu-id="67b98-146">공용 XAML 언어 기본 형식에 대한 기본 제공 형식</span><span class="sxs-lookup"><span data-stu-id="67b98-146">Built-in Types for Common XAML Language Primitives</span></span>](built-in-types-for-common-xaml-language-primitives.md)
- [<span data-ttu-id="67b98-147">XAML의 제네릭</span><span class="sxs-lookup"><span data-stu-id="67b98-147">Generics in XAML</span></span>](generics-in-xaml.md)

---
title: 런타임 지시문(rd.xml) 구성 파일 참조
ms.date: 03/30/2017
ms.assetid: 8241523f-d8e1-4fb6-bf6a-b29bfe07b38a
ms.openlocfilehash: f4c51dc269775d14d395cb464b3787cc987e086d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128135"
---
# <a name="runtime-directives-rdxml-configuration-file-reference"></a><span data-ttu-id="9184a-102">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="9184a-102">Runtime Directives (rd.xml) Configuration File Reference</span></span>

<span data-ttu-id="9184a-103">런타임 지시문(.rd.xml) 파일은 지정된 프로그램 요소를 리플렉션에 사용할 수 있는지 여부를 지정하는 XML 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-103">A runtime directives (.rd.xml) file is an XML configuration file that specifies whether designated program elements are available for reflection.</span></span> <span data-ttu-id="9184a-104">런타임 지시문 파일의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-104">Here’s an example of a runtime directives file:</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Namespace Name="Contoso.Cloud.AppServices" Serialize="Required Public" />
    <Namespace Name="ContosoClient.ViewModels" Serialize="Required Public" />
    <Namespace Name="ContosoClient.DataModel" Serialize="Required Public" />
    <Namespace Name="Contoso.Reader.UtilityLib" Serialize="Required Public" />

    <Namespace Name="System.Collections.ObjectModel" >
      <TypeInstantiation Name="ObservableCollection"
            Arguments="ContosoClient.DataModel.ProductItem" Serialize="Public" />
      <TypeInstantiation Name="ReadOnlyObservableCollection"
            Arguments="ContosoClient.DataModel.ProductGroup" Serialize="Public" />
    </Namespace>
  </Application>
</Directives>
```

## <a name="the-structure-of-a-runtime-directives-file"></a><span data-ttu-id="9184a-105">지시문 런타임 파일의 구조</span><span class="sxs-lookup"><span data-stu-id="9184a-105">The structure of a runtime directives file</span></span>

<span data-ttu-id="9184a-106">런타임 지시문 파일은 `http://schemas.microsoft.com/netfx/2013/01/metadata` 네임스페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-106">The runtime directives file uses the `http://schemas.microsoft.com/netfx/2013/01/metadata` namespace.</span></span>

<span data-ttu-id="9184a-107">루트 요소는 [Directives](directives-element-net-native.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-107">The root element is the [Directives](directives-element-net-native.md) element.</span></span> <span data-ttu-id="9184a-108">이 요소는 다음 구조에 나와 있는 것처럼 [Library](library-element-net-native.md) 요소와 [Application](application-element-net-native.md) 요소를 포함하지 않을 수도 있고 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-108">It can contain zero or more [Library](library-element-net-native.md) elements, and zero or one [Application](application-element-net-native.md) element, as shown in the following structure.</span></span> <span data-ttu-id="9184a-109">[Application](application-element-net-native.md) 요소의 특성은 애플리케이션 전체 런타임 리플렉션 정책을 정의할 수도 있고 자식 요소의 컨테이너로 사용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-109">The attributes of the [Application](application-element-net-native.md) element can define application-wide runtime reflection policy, or it can serve as a container for child elements.</span></span> <span data-ttu-id="9184a-110">반면 [Library](library-element-net-native.md) 요소는 단순한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-110">The [Library](library-element-net-native.md) element, on the other hand, is simply a container.</span></span> <span data-ttu-id="9184a-111">[Application](application-element-net-native.md) 및 [Library](library-element-net-native.md) 요소의 자식은 리플렉션에 사용할 수 있는 형식, 메서드, 필드, 속성 및 이벤트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-111">The children of the [Application](application-element-net-native.md) and [Library](library-element-net-native.md) elements define the types, methods, fields, properties, and events that are available for reflection.</span></span>

<span data-ttu-id="9184a-112">참조 정보를 확인하려면 다음 구조체의 요소를 선택하거나 [런타임 지시문 요소](runtime-directive-elements.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9184a-112">For reference information, choose elements from the following structure or see [Runtime Directive Elements](runtime-directive-elements.md).</span></span> <span data-ttu-id="9184a-113">다음 계층 구조에서 줄임표는 재귀 구조를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-113">In the following hierarchy, the ellipsis marks a recursive structure.</span></span> <span data-ttu-id="9184a-114">괄호 안의 정보는 해당 요소가 필수 항목인지 선택적 항목인지와 요소가 사용되는 경우 허용되는 인스턴스 수(하나 또는 여러 개)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-114">The information in brackets indicates whether that element is optional or required, and if it is used, how many instances (one or many) are allowed.</span></span>

<span data-ttu-id="9184a-115">[지시문](directives-element-net-native.md) [1:1] [응용 프로그램](application-element-net-native.md) [0:1] [어셈블리](assembly-element-net-native.md) [0: m] [네임 스페이스](namespace-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="9184a-115">[Directives](directives-element-net-native.md) [1:1] [Application](application-element-net-native.md) [0:1] [Assembly](assembly-element-net-native.md) [0:M] [Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="9184a-116">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-116">.</span></span> <span data-ttu-id="9184a-117">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-117">.</span></span>
<span data-ttu-id="9184a-118">[0: M]을 [입력](type-element-net-native.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-118">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="9184a-119">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-119">.</span></span> <span data-ttu-id="9184a-120">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-120">.</span></span>
<span data-ttu-id="9184a-121">[Typeinstantiation](typeinstantiation-element-net-native.md) (생성 된 제네릭 형식) [0: M].</span><span class="sxs-lookup"><span data-stu-id="9184a-121">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="9184a-122">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-122">.</span></span> <span data-ttu-id="9184a-123">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-123">.</span></span>
<span data-ttu-id="9184a-124">[네임 스페이스](namespace-element-net-native.md) [0: m] [네임 스페이스](namespace-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="9184a-124">[Namespace](namespace-element-net-native.md) [0:M] [Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="9184a-125">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-125">.</span></span> <span data-ttu-id="9184a-126">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-126">.</span></span>
<span data-ttu-id="9184a-127">[0: M]을 [입력](type-element-net-native.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-127">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="9184a-128">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-128">.</span></span> <span data-ttu-id="9184a-129">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-129">.</span></span>
<span data-ttu-id="9184a-130">[Typeinstantiation](typeinstantiation-element-net-native.md) (생성 된 제네릭 형식) [0: M].</span><span class="sxs-lookup"><span data-stu-id="9184a-130">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="9184a-131">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-131">.</span></span> <span data-ttu-id="9184a-132">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-132">.</span></span>
<span data-ttu-id="9184a-133">[0: m] 형식 (포함 형식의 [하위](subtypes-element-net-native.md) 클래스) [O:1] [형식](type-element-net-native.md) [0: m]을 [입력](type-element-net-native.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-133">[Type](type-element-net-native.md) [0:M] [Subtypes](subtypes-element-net-native.md) (subclasses of the containing type) [O:1] [Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="9184a-134">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-134">.</span></span> <span data-ttu-id="9184a-135">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-135">.</span></span>
<span data-ttu-id="9184a-136">[Typeinstantiation](typeinstantiation-element-net-native.md) (생성 된 제네릭 형식) [0: M].</span><span class="sxs-lookup"><span data-stu-id="9184a-136">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="9184a-137">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-137">.</span></span> <span data-ttu-id="9184a-138">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-138">.</span></span>
<span data-ttu-id="9184a-139">[Attributeimplies](attributeimplies-element-net-native.md) (특성을 포함 하는 형식) [O:1 [] GenericParameter](genericparameter-element-net-native.md) [0: m] [메서드](method-element-net-native.md) [0: m] [매개](parameter-element-net-native.md) 변수 [0: m] [typeparameter](typeparameter-element-net-native.md) [0: m] [GenericParameter](genericparameter-element-net-native.md) [0: m] [methodinstantiation](methodinstantiation-element-net-native.md) ( 생성 된 제네릭 메서드) [0: M] [속성](property-element-net-native.md) [0: m] [필드](field-element-net-native.md) [0: m] [이벤트](event-element-net-native.md) [0: m] [typeinstantiation](typeinstantiation-element-net-native.md) (생성 된 제네릭 형식) [0: m] [형식](type-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="9184a-139">[AttributeImplies](attributeimplies-element-net-native.md) (containing type is an attribute) [O:1] [GenericParameter](genericparameter-element-net-native.md) [0:M] [Method](method-element-net-native.md) [0:M] [Parameter](parameter-element-net-native.md) [0:M] [TypeParameter](typeparameter-element-net-native.md) [0:M] [GenericParameter](genericparameter-element-net-native.md) [0:M] [MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](property-element-net-native.md) [0:M] [Field](field-element-net-native.md) [0:M] [Event](event-element-net-native.md) [0:M] [TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] [Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="9184a-140">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-140">.</span></span> <span data-ttu-id="9184a-141">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-141">.</span></span>
<span data-ttu-id="9184a-142">[Typeinstantiation](typeinstantiation-element-net-native.md) (생성 된 제네릭 형식) [0: M].</span><span class="sxs-lookup"><span data-stu-id="9184a-142">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="9184a-143">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-143">.</span></span> <span data-ttu-id="9184a-144">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-144">.</span></span>
<span data-ttu-id="9184a-145">[메서드](method-element-net-native.md) [0: m] [매개](parameter-element-net-native.md) 변수 [0: m] [typeparameter](typeparameter-element-net-native.md) [0: M [] GenericParameter](genericparameter-element-net-native.md) [0: m [] methodinstantiation](methodinstantiation-element-net-native.md) (생성 된 제네릭 메서드) [0: m] [속성](property-element-net-native.md) [0: m] [필드](field-element-net-native.md) [0: m] [이벤트](event-element-net-native.md) [ [0: m] Library](library-element-net-native.md) [0: m] [어셈블리](assembly-element-net-native.md) [0: m] [네임 스페이스](namespace-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="9184a-145">[Method](method-element-net-native.md) [0:M] [Parameter](parameter-element-net-native.md) [0:M] [TypeParameter](typeparameter-element-net-native.md) [0:M] [GenericParameter](genericparameter-element-net-native.md) [0:M] [MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](property-element-net-native.md) [0:M] [Field](field-element-net-native.md) [0:M] [Event](event-element-net-native.md) [0:M] [Library](library-element-net-native.md) [0:M] [Assembly](assembly-element-net-native.md) [0:M] [Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="9184a-146">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-146">.</span></span> <span data-ttu-id="9184a-147">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-147">.</span></span>
<span data-ttu-id="9184a-148">[0: M]을 [입력](type-element-net-native.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-148">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="9184a-149">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-149">.</span></span> <span data-ttu-id="9184a-150">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-150">.</span></span>
<span data-ttu-id="9184a-151">[Typeinstantiation](typeinstantiation-element-net-native.md) (생성 된 제네릭 형식) [0: M].</span><span class="sxs-lookup"><span data-stu-id="9184a-151">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="9184a-152">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-152">.</span></span> <span data-ttu-id="9184a-153">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-153">.</span></span>
<span data-ttu-id="9184a-154">[네임 스페이스](namespace-element-net-native.md) [0: m] [네임 스페이스](namespace-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="9184a-154">[Namespace](namespace-element-net-native.md) [0:M] [Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="9184a-155">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-155">.</span></span> <span data-ttu-id="9184a-156">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-156">.</span></span>
<span data-ttu-id="9184a-157">[0: M]을 [입력](type-element-net-native.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-157">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="9184a-158">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-158">.</span></span> <span data-ttu-id="9184a-159">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-159">.</span></span>
<span data-ttu-id="9184a-160">[Typeinstantiation](typeinstantiation-element-net-native.md) (생성 된 제네릭 형식) [0: M].</span><span class="sxs-lookup"><span data-stu-id="9184a-160">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="9184a-161">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-161">.</span></span> <span data-ttu-id="9184a-162">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-162">.</span></span>
<span data-ttu-id="9184a-163">[0: m] 형식 (포함 형식의 [하위](subtypes-element-net-native.md) 클래스) [O:1] [형식](type-element-net-native.md) [0: m]을 [입력](type-element-net-native.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-163">[Type](type-element-net-native.md) [0:M] [Subtypes](subtypes-element-net-native.md) (subclasses of the containing type) [O:1] [Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="9184a-164">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-164">.</span></span> <span data-ttu-id="9184a-165">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-165">.</span></span>
<span data-ttu-id="9184a-166">[Typeinstantiation](typeinstantiation-element-net-native.md) (생성 된 제네릭 형식) [0: M].</span><span class="sxs-lookup"><span data-stu-id="9184a-166">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="9184a-167">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-167">.</span></span> <span data-ttu-id="9184a-168">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-168">.</span></span>
<span data-ttu-id="9184a-169">[Attributeimplies](attributeimplies-element-net-native.md) (특성 포함) [O:1] [GenericParameter](genericparameter-element-net-native.md) [0: m] [메서드](method-element-net-native.md) [0: m] [methodinstantiation](methodinstantiation-element-net-native.md) (생성 된 제네릭 메서드) [0: m] [속성](property-element-net-native.md) [0: m] [필드](field-element-net-native.md) [0: m] [이벤트](event-element-net-native.md) [0 : M] [Typeinstantiation](typeinstantiation-element-net-native.md) (생성 된 제네릭 형식) [0: m] [형식](type-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="9184a-169">[AttributeImplies](attributeimplies-element-net-native.md) (containing type is an attribute) [O:1] [GenericParameter](genericparameter-element-net-native.md) [0:M] [Method](method-element-net-native.md) [0:M] [MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](property-element-net-native.md) [0:M] [Field](field-element-net-native.md) [0:M] [Event](event-element-net-native.md) [0:M] [TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] [Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="9184a-170">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-170">.</span></span> <span data-ttu-id="9184a-171">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-171">.</span></span>
<span data-ttu-id="9184a-172">[Typeinstantiation](typeinstantiation-element-net-native.md) (생성 된 제네릭 형식) [0: M].</span><span class="sxs-lookup"><span data-stu-id="9184a-172">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="9184a-173">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-173">.</span></span> <span data-ttu-id="9184a-174">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-174">.</span></span>
<span data-ttu-id="9184a-175">[메서드](method-element-net-native.md) [0: M] [methodinstantiation](methodinstantiation-element-net-native.md) (생성 된 제네릭 메서드) [0: m] [속성](property-element-net-native.md) [0: m] [필드](field-element-net-native.md) [0: m] [이벤트](event-element-net-native.md) [0: m]</span><span class="sxs-lookup"><span data-stu-id="9184a-175">[Method](method-element-net-native.md) [0:M] [MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](property-element-net-native.md) [0:M] [Field](field-element-net-native.md) [0:M] [Event](event-element-net-native.md) [0:M]</span></span>

<span data-ttu-id="9184a-176">[Application](application-element-net-native.md) 요소는 특성을 포함할 수 없거나 [런타임 지시문 및 정책 섹션](#Directives)에서 설명하는 정책 특성을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-176">The [Application](application-element-net-native.md) element can have no attributes, or it can have the policy attributes discussed in the [Runtime directive and policy section](#Directives).</span></span>

<span data-ttu-id="9184a-177">[Library](library-element-net-native.md) 요소는 파일 이름 확장명을 포함하지 않는 라이브러리나 어셈블리의 이름을 지정하는 단일 특성(`Name`)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-177">A [Library](library-element-net-native.md) element has a single attribute, `Name`, that specifies the name of a library or assembly, without its file extension.</span></span> <span data-ttu-id="9184a-178">예를 들어 다음 [Library](library-element-net-native.md) 요소는 Extensions.dll 어셈블리에 적용되는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-178">For example, the following [Library](library-element-net-native.md) element applies to an assembly named Extensions.dll.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
     <!-- Child elements go here -->
  </Application>
  <Library Name="Extensions">
     <!-- Child elements go here -->
  </Library>
</Directives>
```

<a name="Directives"></a>

## <a name="runtime-directives-and-policy"></a><span data-ttu-id="9184a-179">런타임 지시문 및 정책</span><span class="sxs-lookup"><span data-stu-id="9184a-179">Runtime directives and policy</span></span>

<span data-ttu-id="9184a-180">[Application](application-element-net-native.md) 요소 자체와 [Library](library-element-net-native.md) 및 [Application](application-element-net-native.md) 요소의 자식 요소는 정책을 표현합니다. 즉, 앱이 프로그램 요소에 리플렉션을 적용할 수 있는 방식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-180">The [Application](application-element-net-native.md) element itself and the child elements of the [Library](library-element-net-native.md) and [Application](application-element-net-native.md) elements express policy; that is, they define the way in which an app can apply reflection to a program element.</span></span> <span data-ttu-id="9184a-181">정책 형식은 요소의 특성에 의해 정의됩니다(예: `Serialize`).</span><span class="sxs-lookup"><span data-stu-id="9184a-181">The policy type is defined by an attribute of the element (for example, `Serialize`).</span></span> <span data-ttu-id="9184a-182">정책 값은 특성의 값으로 정의됩니다(예: `Serialize="Required"`).</span><span class="sxs-lookup"><span data-stu-id="9184a-182">The policy value is defined by the attribute’s value (for example, `Serialize="Required"`).</span></span>

<span data-ttu-id="9184a-183">요소의 특성으로 지정된 정책은 해당 정책에 대해 값을 지정하지 않는 모든 자식 요소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-183">Any policy specified by an attribute of an element applies to all child elements that don’t specify a value for that policy.</span></span> <span data-ttu-id="9184a-184">예를 들어 정책이 [Type](type-element-net-native.md) 요소로 지정된 경우 정책이 명시적으로 지정되지 않은 모든 포함된 형식 및 멤버에 해당 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-184">For example, if a policy is specified by a [Type](type-element-net-native.md) element, that policy applies to all contained types and members for which a policy is not explicitly specified.</span></span>

<span data-ttu-id="9184a-185">[Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) 및 [Type](type-element-net-native.md) 요소로 표현할 수 있는 정책은 [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md) 및 [Event](event-element-net-native.md) 요소로 개별 멤버에 대해 표현할 수 있는 정책과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-185">The policy that can be expressed by the [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md), and [Type](type-element-net-native.md) elements differs from the policy that can be expressed for individual members (by the [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md), and [Event](event-element-net-native.md) elements).</span></span>

### <a name="specifying-policy-for-assemblies-namespaces-and-types"></a><span data-ttu-id="9184a-186">어셈블리, 네임스페이스 및 형식에 대한 정책 지정</span><span class="sxs-lookup"><span data-stu-id="9184a-186">Specifying policy for assemblies, namespaces, and types</span></span>

<span data-ttu-id="9184a-187">[Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) 및 [Type](type-element-net-native.md) 요소는 다음 정책 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-187">The [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md), and [Type](type-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="9184a-188">`Activate`</span><span class="sxs-lookup"><span data-stu-id="9184a-188">`Activate`.</span></span> <span data-ttu-id="9184a-189">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-189">Controls runtime access to constructors, to enable activation of instances.</span></span>

- <span data-ttu-id="9184a-190">`Browse`</span><span class="sxs-lookup"><span data-stu-id="9184a-190">`Browse`.</span></span> <span data-ttu-id="9184a-191">프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-191">Controls querying for information about program elements but does not enable any runtime access.</span></span>

- <span data-ttu-id="9184a-192">`Dynamic`</span><span class="sxs-lookup"><span data-stu-id="9184a-192">`Dynamic`.</span></span> <span data-ttu-id="9184a-193">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-193">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>

- <span data-ttu-id="9184a-194">`Serialize`</span><span class="sxs-lookup"><span data-stu-id="9184a-194">`Serialize`.</span></span> <span data-ttu-id="9184a-195">Newtonsoft JSON serializer 등의 타사 라이브러리를 통해 형식 인스턴스를 serialize 및 deserialize할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-195">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and serialized by third-party libraries such as the Newtonsoft JSON serializer.</span></span>

- <span data-ttu-id="9184a-196">`DataContractSerializer`</span><span class="sxs-lookup"><span data-stu-id="9184a-196">`DataContractSerializer`.</span></span> <span data-ttu-id="9184a-197"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-197">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="9184a-198">`DataContractJsonSerializer`</span><span class="sxs-lookup"><span data-stu-id="9184a-198">`DataContractJsonSerializer`.</span></span> <span data-ttu-id="9184a-199"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-199">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="9184a-200">`XmlSerializer`</span><span class="sxs-lookup"><span data-stu-id="9184a-200">`XmlSerializer`.</span></span> <span data-ttu-id="9184a-201"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-201">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="9184a-202">`MarshalObject`</span><span class="sxs-lookup"><span data-stu-id="9184a-202">`MarshalObject`.</span></span> <span data-ttu-id="9184a-203">WinRT 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-203">Controls policy for marshaling reference types to WinRT and COM.</span></span>

- <span data-ttu-id="9184a-204">`MarshalDelegate`</span><span class="sxs-lookup"><span data-stu-id="9184a-204">`MarshalDelegate`.</span></span> <span data-ttu-id="9184a-205">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-205">Controls policy for marshaling delegate types as function pointers to native code.</span></span>

- <span data-ttu-id="9184a-206">`MarshalStructure`.</span><span class="sxs-lookup"><span data-stu-id="9184a-206">`MarshalStructure` .</span></span> <span data-ttu-id="9184a-207">구조체를 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-207">Controls policy for marshaling structures to native code.</span></span>

<span data-ttu-id="9184a-208">이러한 정책 형식과 연관된 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-208">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="9184a-209">`All`</span><span class="sxs-lookup"><span data-stu-id="9184a-209">`All`.</span></span> <span data-ttu-id="9184a-210">도구 체인에서 제거하지 않는 모든 형식과 멤버에 대해 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-210">Enable the policy for all types and members that the tool chain does not remove.</span></span>

- <span data-ttu-id="9184a-211">`Auto`</span><span class="sxs-lookup"><span data-stu-id="9184a-211">`Auto`.</span></span> <span data-ttu-id="9184a-212">기본 동작을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-212">Use the default behavior.</span></span> <span data-ttu-id="9184a-213">정책을 지정하지 않는 것은 부모 요소에 의해 정책이 재정의되는 등의 경우를 제외하면 해당 정책을 `Auto`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-213">(Not specifying a policy is equivalent to setting that policy to `Auto` unless that policy is overridden, for example by a parent element.)</span></span>

- <span data-ttu-id="9184a-214">`Excluded`</span><span class="sxs-lookup"><span data-stu-id="9184a-214">`Excluded`.</span></span> <span data-ttu-id="9184a-215">프로그램 요소에 대한 정책을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-215">Disable the policy for the program element.</span></span>

- <span data-ttu-id="9184a-216">`Public`</span><span class="sxs-lookup"><span data-stu-id="9184a-216">`Public`.</span></span> <span data-ttu-id="9184a-217">도구 체인이 멤버를 불필요한 것으로 결정하여 제거하는 경우가 아니면 public 형식 또는 멤버에 대해서는 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-217">Enable the policy for public types or members unless the tool chain determines that the member is unnecessary and therefore removes it.</span></span> <span data-ttu-id="9184a-218">멤버가 제거되는 경우에는 `Required Public`을 사용하여 멤버를 유지하고 리플렉션 기능이 포함되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-218">(In the latter case, you must use `Required Public` to ensure that the member is kept and has reflection capabilities.)</span></span>

- <span data-ttu-id="9184a-219">`PublicAndInternal`</span><span class="sxs-lookup"><span data-stu-id="9184a-219">`PublicAndInternal`.</span></span> <span data-ttu-id="9184a-220">도구 체인에서 제거하지 않는 public 및 내부 형식이나 멤버에 대해 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-220">Enable the policy for public and internal types or members if the tool chain doesn't remove them.</span></span>

- <span data-ttu-id="9184a-221">`Required Public`</span><span class="sxs-lookup"><span data-stu-id="9184a-221">`Required Public`.</span></span> <span data-ttu-id="9184a-222">사용 여부에 관계없이 도구 체인이 public 형식과 멤버를 유지해야 하도록 지정하고 해당 형식과 멤버에 대해 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-222">Require the tool chain to keep public types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="9184a-223">`Required PublicAndInternal`</span><span class="sxs-lookup"><span data-stu-id="9184a-223">`Required PublicAndInternal`.</span></span> <span data-ttu-id="9184a-224">사용 여부에 관계없이 도구 체인이 public 및 내부 형식과 멤버를 모두 유지해야 하도록 지정하고 해당 형식과 멤버에 대해 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-224">Require the tool chain to keep both public and internal types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="9184a-225">`Required All`</span><span class="sxs-lookup"><span data-stu-id="9184a-225">`Required All`.</span></span> <span data-ttu-id="9184a-226">사용 여부에 관계없이 도구 체인이 모든 형식과 멤버를 유지해야 하도록 지정하고 해당 형식과 멤버에 대해 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-226">Require the tool chain to keep all types and members whether or not they are used, and enable the policy for them.</span></span>

<span data-ttu-id="9184a-227">예를 들어 다음 런타임 지시문 파일은 DataClasses.dll 어셈블리의 모든 형식과 멤버에 대한 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-227">For example, the following runtime directives file defines policy for all types and members in the assembly DataClasses.dll.</span></span> <span data-ttu-id="9184a-228">이 정책은 모든 public 속성의 serialization에 대해 리플렉션을 사용하도록 설정하고, 모든 형식 및 형식 멤버를 검색할 수 있도록 설정하고, `Dynamic` 특성을 통해 모든 형식을 활성화할 수 있도록 설정하고, 모든 public 형식 및 멤버에 대해 리플렉션을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-228">It enables reflection for serialization of all public properties, enables browsing for all types and type members, enables activation for all types (because of the `Dynamic` attribute), and enables reflection for all public types and members.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"
                Browse="All" Activate="PublicAndInternal"
                Dynamic="Public"  />
   </Application>
   <Library Name="UtilityLibrary">
     <!-- Child elements go here -->
   </Library>
</Directives>
```

### <a name="specifying-policy-for-members"></a><span data-ttu-id="9184a-229">멤버에 대한 정책 지정</span><span class="sxs-lookup"><span data-stu-id="9184a-229">Specifying policy for members</span></span>

<span data-ttu-id="9184a-230">[Property](property-element-net-native.md) 및 [Field](field-element-net-native.md) 요소는 다음 정책 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-230">The [Property](property-element-net-native.md) and [Field](field-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="9184a-231">`Browse` - 이 멤버에 대한 정보 쿼리는 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-231">`Browse` - Controls querying for information about this member but does not enable any runtime access.</span></span>

- <span data-ttu-id="9184a-232">`Dynamic` - 동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-232">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="9184a-233">또한 포함 형식에 대한 정보 쿼리도 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-233">Also controls querying for information about the containing type.</span></span>

- <span data-ttu-id="9184a-234">`Serialize` - Newtonsoft JSON serializer 등의 라이브러리를 통해 형식 인스턴스를 serialize 및 deserialize할 수 있도록 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-234">`Serialize` - Controls runtime access to the member to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span> <span data-ttu-id="9184a-235">이 정책은 생성자, 필드 및 속성에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-235">This policy can be applied to constructors, fields, and properties.</span></span>

<span data-ttu-id="9184a-236">[Method](method-element-net-native.md) 및 [Event](event-element-net-native.md) 요소는 다음 정책 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-236">The [Method](method-element-net-native.md) and [Event](event-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="9184a-237">`Browse` - 이 멤버에 대한 정보 쿼리는 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-237">`Browse` - Controls querying for information about this member but doesn’t enable any runtime access.</span></span>

- <span data-ttu-id="9184a-238">`Dynamic` - 동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-238">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="9184a-239">또한 포함 형식에 대한 정보 쿼리도 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-239">Also controls querying for information about the containing type.</span></span>

 <span data-ttu-id="9184a-240">이러한 정책 형식과 연관된 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-240">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="9184a-241">`Auto` - 기본 동작을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-241">`Auto` - Use the default behavior.</span></span> <span data-ttu-id="9184a-242">특정 요소가 정책을 재정의하는 경우를 제외하면 정책을 지정하지 않는 것은 정책을 `Auto`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-242">(Not specifying a policy is equivalent to setting that policy to `Auto` unless something overrides it.)</span></span>

- <span data-ttu-id="9184a-243">`Excluded` - 멤버에 대한 메타데이터를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-243">`Excluded` - Never include metadata for the member.</span></span>

- <span data-ttu-id="9184a-244">`Included` - 출력에 부모 형식이 있으면 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-244">`Included` - Enable the policy if the parent type is present in the output.</span></span>

- <span data-ttu-id="9184a-245">`Required` - 특정 멤버가 사용되지 않는 것으로 확인되더라도 도구 체인이 해당 멤버를 유지해야 하도록 지정하고 해당 멤버에 대해 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-245">`Required` - Require the tool chain to keep this member even if appears to be unused, and enable policy for it.</span></span>

## <a name="runtime-directives-file-semantics"></a><span data-ttu-id="9184a-246">런타임 지시문 파일 의미</span><span class="sxs-lookup"><span data-stu-id="9184a-246">Runtime directives file semantics</span></span>

<span data-ttu-id="9184a-247">상위 및 하위 요소 둘 다에 대해 정책을 동시에 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-247">Policy can be defined simultaneously for both higher-level and lower-level elements.</span></span> <span data-ttu-id="9184a-248">예를 들어 어셈블리 및 해당 어셈블리에 포함된 일부 형식에 대한 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-248">For example, policy can be defined for an assembly, and for some of the types contained in that assembly.</span></span> <span data-ttu-id="9184a-249">표시되지 않는 특정 하위 요소는 부모의 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-249">If a particular lower-level element is not represented, it inherits the policy of its parent.</span></span> <span data-ttu-id="9184a-250">예를 들어 `Assembly` 요소는 있는데 `Type` 요소는 없으면 `Assembly` 요소에 지정된 정책이 어셈블리의 각 형식에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-250">For example, if an `Assembly` element is present but `Type` elements are not, the policy specified in the `Assembly` element applies to each type in the assembly.</span></span> <span data-ttu-id="9184a-251">또한 여러 요소가 같은 프로그램 요소에 정책을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-251">Multiple elements can also apply policy to the same program element.</span></span> <span data-ttu-id="9184a-252">예를 들어 개별 [Assembly](assembly-element-net-native.md) 요소가 같은 어셈블리에 대해 같은 정책 요소를 각기 다르게 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-252">For example, separate [Assembly](assembly-element-net-native.md) elements might define the same policy element for the same assembly differently.</span></span> <span data-ttu-id="9184a-253">다음 섹션에서는 이러한 경우 특정 형식에 대한 정책을 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-253">The following sections explain how the policy for a particular type is resolved in those cases.</span></span>

<span data-ttu-id="9184a-254">제네릭 형식이나 메서드의 [Type](type-element-net-native.md) 또는 [Method](method-element-net-native.md) 요소는 자체 정책을 포함하지 않는 모든 인스턴스화에 해당 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-254">A [Type](type-element-net-native.md) or [Method](method-element-net-native.md) element of a generic type or method applies its policy to all instantiations that do not have their own policy.</span></span> <span data-ttu-id="9184a-255">예를 들어 `Type`에 대해 정책을 지정하는 <xref:System.Collections.Generic.List%601> 요소는 해당 제네릭 형식의 생성된 모든 인스턴스에 적용됩니다. 단, `List<Int32>` 요소가 `TypeInstantiation`와 같은 생성된 특정 제네릭 형식에 대해 정책을 재정의하는 경우는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-255">For example, a `Type` element that specifies policy for <xref:System.Collections.Generic.List%601> applies to all constructed instances of that generic type, unless it's overridden for a particular constructed generic type (such as a `List<Int32>`) by a `TypeInstantiation` element.</span></span> <span data-ttu-id="9184a-256">이러한 경우가 아니면 요소는 명명된 프로그램 요소에 대해 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-256">Otherwise, elements define policy for the program element named.</span></span>

<span data-ttu-id="9184a-257">요소가 모호한 경우 엔진은 일치하는 항목을 찾으며 정확히 일치하는 항목이 발견되면 해당 항목을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-257">When an element is ambiguous, the engine looks for matches, and if it finds an exact match, it will use it.</span></span> <span data-ttu-id="9184a-258">일치하는 항목이 여러 개이면 경고나 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-258">If it finds multiple matches, there will be a warning or error.</span></span>

### <a name="if-two-directives-apply-policy-to-the-same-program-element"></a><span data-ttu-id="9184a-259">두 지시문이 같은 프로그램 요소에 정책을 적용하는 경우</span><span class="sxs-lookup"><span data-stu-id="9184a-259">If two directives apply policy to the same program element</span></span>

<span data-ttu-id="9184a-260">서로 다른 런타임 지시문 파일의 두 요소가 어셈블리나 형식 등의 같은 프로그램 요소에 대한 동일 정책 형식을 각기 다른 값으로 설정하려는 경우에는 다음과 같은 방법으로 충돌을 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-260">If two elements in different runtime directives files try to set the same policy type for the same program element (such as an assembly or type) to different values, the conflict is resolved as follows:</span></span>

1. <span data-ttu-id="9184a-261">`Excluded` 요소가 있으면 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-261">If the `Excluded` element is present, it has precedence.</span></span>

2. <span data-ttu-id="9184a-262">`Required`인 항목이 `Required`가 아닌 항목보다 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-262">`Required` has precedence over not `Required`.</span></span>

3. <span data-ttu-id="9184a-263">`All`, `PublicAndInternal`, `Public`이 순서대로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-263">`All` has precedence over `PublicAndInternal`, which has precedence over `Public`.</span></span>

4. <span data-ttu-id="9184a-264">명시적 설정이 `Auto`보다 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-264">Any explicit setting has precedence over `Auto`.</span></span>

<span data-ttu-id="9184a-265">예를 들어 프로젝트 하나에 다음과 같은 두 런타임 지시문 파일이 포함되어 있으면 DataClasses.dll의 serialization 정책이 `Required Public` 및 `All` 둘 다로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-265">For example, if a single project includes the following two runtime directives files, the serialization policy for DataClasses.dll is set to both `Required Public` and `All`.</span></span> <span data-ttu-id="9184a-266">이 경우 serialization 정책은 `Required All`로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-266">In this case, the serialization policy would be resolved as `Required All`.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"/>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="All" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

<span data-ttu-id="9184a-267">그러나 단일 런타임 지시문 파일의 두 지시문이 같은 프로그램 요소에 대해 같은 정책 형식을 설정하려고 하면 XML 스키마 정의 도구에 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-267">However, if two directives in a single runtime directives file try to set the same policy type for the same program element, the XML Scheme Definition tool displays an error message.</span></span>

### <a name="if-child-and-parent-elements-apply-the-same-policy-type"></a><span data-ttu-id="9184a-268">자식 및 부모 요소가 같은 정책 형식을 적용하는 경우</span><span class="sxs-lookup"><span data-stu-id="9184a-268">If child and parent elements apply the same policy type</span></span>

<span data-ttu-id="9184a-269">자식 요소는 `Excluded` 설정을 포함하여 부모 요소를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-269">Child elements override their parent elements, including the `Excluded` setting.</span></span> <span data-ttu-id="9184a-270">대개 이러한 재정의로 인해 `Auto`를 지정하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-270">Overriding is the main reason you would want to specify `Auto`.</span></span>

<span data-ttu-id="9184a-271">다음 예에서는 `DataClasses`에 포함되어 있지 않은 `DataClasses.ViewModels`의 모든 항목에 대한 serialization 정책 설정은 `Required Public`이 되고 `DataClasses` 및 `DataClasses.ViewModels`에 모두 포함되어 있는 모든 항목에 대한 serialization 정책 설정은 `All`이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-271">In the following example, the serialization policy setting for everything in `DataClasses` that’s not in `DataClasses.ViewModels` would be `Required Public`, and everything that's in both `DataClasses` and `DataClasses.ViewModels` would be `All`.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="if-open-generics-and-instantiated-elements-apply-the-same-policy-type"></a><span data-ttu-id="9184a-272">개방형 제네릭 및 인스턴스화된 요소 형식이 같은 정책을 적용하는 경우</span><span class="sxs-lookup"><span data-stu-id="9184a-272">If open generics and instantiated elements apply the same policy type</span></span>

<span data-ttu-id="9184a-273">다음 예제에서는 엔진이 다른 이유로 인해 `Dictionary<int,int>` 정책을 적용해야 하는 경우에만 `Browse`에 `Browse` 정책이 할당됩니다(그렇지 않으면 이 정책이 기본 동작임). <xref:System.Collections.Generic.Dictionary%602>의 다른 모든 인스턴스화에서는 모든 구성원을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-273">In the following example, `Dictionary<int,int>` is assigned the `Browse` policy only if the engine has another reason to give it the `Browse` policy (which would otherwise be the default behavior); every other instantiation of <xref:System.Collections.Generic.Dictionary%602> will have all of its members browsable.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
      <Namespace Name="DataClasses.Generics" />
      <Type Name="Dictionary" Browse="All" />
      <TypeInstantiation Name="Dictionary"
                         Arguments="System.Int32,System.Int32" Browse="Auto" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="how-policy-is-inferred"></a><span data-ttu-id="9184a-274">정책을 유추하는 방법</span><span class="sxs-lookup"><span data-stu-id="9184a-274">How policy is inferred</span></span>

<span data-ttu-id="9184a-275">각 정책 형식에는 해당 정책 형식의 유무가 다른 구문에 주는 영향을 결정하는 여러 규칙 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-275">Each policy type has a different set of rules that determine how the presence of that policy type affects other constructs.</span></span>

#### <a name="the-effect-of-browse-policy"></a><span data-ttu-id="9184a-276">Browse 정책의 영향</span><span class="sxs-lookup"><span data-stu-id="9184a-276">The effect of Browse policy</span></span>

<span data-ttu-id="9184a-277">형식에 `Browse` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-277">Applying the `Browse` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="9184a-278">해당 형식의 기본 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-278">The base type of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-279">형식이 인스턴스화된 제네릭인 경우 인스턴스화되지 않은 형식 버전이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-279">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-280">형식이 대리자인 경우에는 형식의 `Invoke` 메서드가 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-280">If the type is a delegate, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="9184a-281">형식의 각 인터페이스가 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-281">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-282">형식에 적용된 각 특성의 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-282">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-283">형식이 제네릭인 경우 각 제약 조건 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-283">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-284">형식이 제네릭이면 해당 형식이 인스턴스화되는 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-284">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="9184a-285">메서드에 `Browse` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-285">Applying the `Browse` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="9184a-286">메서드의 각 매개 변수 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-286">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-287">해당 메서드의 반환 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-287">The return type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-288">해당 메서드의 포함 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-288">The containing type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-289">메서드가 인스턴스화된 제네릭 메서드인 경우 인스턴스화되지 않은 제네릭 메서드가 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-289">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-290">메서드에 적용된 각 특성의 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-290">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-291">메서드가 제네릭인 경우 각 제약 조건 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-291">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-292">메서드가 제네릭이면 해당 메서드가 인스턴스화되는 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-292">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="9184a-293">필드에 `Browse` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-293">Applying the `Browse` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="9184a-294">필드에 적용된 각 특성의 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-294">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-295">필드의 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-295">The type of the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-296">필드가 속하는 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-296">The type to which the field belongs is marked with the `Browse` policy.</span></span>

#### <a name="the-effect-of-dynamic-policy"></a><span data-ttu-id="9184a-297">Dynamic 정책의 영향</span><span class="sxs-lookup"><span data-stu-id="9184a-297">The effect of Dynamic policy</span></span>

<span data-ttu-id="9184a-298">형식에 `Dynamic` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-298">Applying the `Dynamic` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="9184a-299">해당 형식의 기본 형식이 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-299">The base type of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="9184a-300">형식이 인스턴스화된 제네릭인 경우 인스턴스화되지 않은 형식 버전이 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-300">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="9184a-301">형식이 대리자 형식인 경우에는 형식의 `Invoke` 메서드가 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-301">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="9184a-302">형식의 각 인터페이스가 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-302">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-303">형식에 적용된 각 특성의 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-303">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-304">형식이 제네릭인 경우 각 제약 조건 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-304">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-305">형식이 제네릭이면 해당 형식이 인스턴스화되는 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-305">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="9184a-306">메서드에 `Dynamic` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-306">Applying the `Dynamic` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="9184a-307">메서드의 각 매개 변수 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-307">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-308">해당 메서드의 반환 형식이 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-308">The return type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="9184a-309">해당 메서드의 포함 형식이 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-309">The containing type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="9184a-310">메서드가 인스턴스화된 제네릭 메서드인 경우 인스턴스화되지 않은 제네릭 메서드가 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-310">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-311">메서드에 적용된 각 특성의 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-311">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-312">메서드가 제네릭인 경우 각 제약 조건 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-312">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-313">메서드가 제네릭이면 해당 메서드가 인스턴스화되는 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-313">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-314">`MethodInfo.Invoke`를 통해 메서드를 호출할 수 있으며 <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>를 통해 대리자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-314">The method can be invoked by `MethodInfo.Invoke`, and delegate creation becomes possible by <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="9184a-315">필드에 `Dynamic` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-315">Applying the `Dynamic` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="9184a-316">필드에 적용된 각 특성의 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-316">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-317">필드의 형식이 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-317">The type of the field is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="9184a-318">필드가 속하는 형식이 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-318">The type to which the field belongs is marked with the `Dynamic` policy.</span></span>

#### <a name="the-effect-of-activation-policy"></a><span data-ttu-id="9184a-319">Activation 정책의 영향</span><span class="sxs-lookup"><span data-stu-id="9184a-319">The effect of Activation policy</span></span>

<span data-ttu-id="9184a-320">형식에 Activation 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-320">Applying the Activation policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="9184a-321">형식이 인스턴스화된 제네릭인 경우 인스턴스화되지 않은 형식 버전이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-321">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-322">형식이 대리자 형식인 경우에는 형식의 `Invoke` 메서드가 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-322">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="9184a-323">형식의 생성자가 `Activation` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-323">Constructors of the type are marked with the `Activation` policy.</span></span>

<span data-ttu-id="9184a-324">메서드에 `Activation` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-324">Applying the `Activation` policy to a method involves the following policy change:</span></span>

- <span data-ttu-id="9184a-325"><xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> 및 <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> 메서드를 통해 생성자를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-325">The constructor can be invoked by the <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> and <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="9184a-326">메서드의 경우에는 `Activation` 정책이 생성자에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-326">For methods, the `Activation` policy affects constructors only.</span></span>

<span data-ttu-id="9184a-327">필드에는 `Activation` 정책을 적용해도 아무런 영향이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-327">Applying the `Activation` policy to a field has no effect.</span></span>

#### <a name="the-effect-of-serialize-policy"></a><span data-ttu-id="9184a-328">Serialize 정책의 영향</span><span class="sxs-lookup"><span data-stu-id="9184a-328">The effect of Serialize policy</span></span>

<span data-ttu-id="9184a-329">`Serialize` 정책을 적용하면 일반적인 리플렉션 기반 serializer를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-329">The `Serialize` policy enables the use of common reflection-based serializers.</span></span> <span data-ttu-id="9184a-330">그러나 Microsoft는 타사 serializer의 정확한 리플렉션 액세스 패턴을 확인할 수 없으므로 이 정책이 완전히 적용되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-330">However, because the exact reflection access patterns of non-Microsoft serializers are not known to Microsoft, this policy may not be entirely effective.</span></span>

<span data-ttu-id="9184a-331">형식에 `Serialize` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-331">Applying the `Serialize` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="9184a-332">해당 형식의 기본 형식이 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-332">The base type of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="9184a-333">형식이 인스턴스화된 제네릭인 경우 인스턴스화되지 않은 형식 버전이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-333">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="9184a-334">형식이 대리자 형식인 경우에는 형식의 `Invoke` 메서드가 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-334">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="9184a-335">형식이 열거형이면 해당 형식의 배열이 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-335">If the type is an enumeration, an array of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="9184a-336">형식이 <xref:System.Collections.Generic.IEnumerable%601>를 구현하는 경우 `T`가 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-336">If the type implements <xref:System.Collections.Generic.IEnumerable%601>, `T` is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="9184a-337">형식이 <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601> 또는 <xref:System.Collections.Generic.IReadOnlyList%601>이면 `T[]` 및 <xref:System.Collections.Generic.List%601>는 `Serialize` 정책으로 표시되지만 인터페이스 형식의 멤버는 `Serialize` 정책으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-337">If the type is <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601>, or <xref:System.Collections.Generic.IReadOnlyList%601>, then `T[]` and <xref:System.Collections.Generic.List%601> marked with the `Serialize` policy., but no members of the interface type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="9184a-338">형식이 <xref:System.Collections.Generic.List%601>이면 형식의 멤버는 `Serialize` 정책으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-338">If the type is <xref:System.Collections.Generic.List%601>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="9184a-339">형식이 <xref:System.Collections.Generic.IDictionary%602>이면 <xref:System.Collections.Generic.Dictionary%602>가 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-339">If the type is <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> is marked with the `Serialize` policy.</span></span> <span data-ttu-id="9184a-340">그러나 형식의 멤버는 `Serialize` 정책으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-340">but no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="9184a-341">형식이 <xref:System.Collections.Generic.Dictionary%602>이면 형식의 멤버는 `Serialize` 정책으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-341">If the type is <xref:System.Collections.Generic.Dictionary%602>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="9184a-342">형식이 <xref:System.Collections.Generic.IDictionary%602>를 구현하는 경우 `TKey` 및 `TValue`는 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-342">If the type implements <xref:System.Collections.Generic.IDictionary%602>, `TKey` and `TValue` are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="9184a-343">각 생성자, 각 속성 접근자 및 각 필드가 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-343">Each constructor, each property accessor, and each field is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="9184a-344">메서드에 `Serialize` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-344">Applying the `Serialize` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="9184a-345">포함 형식이 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-345">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="9184a-346">해당 메서드의 반환 형식이 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-346">The return type of the method is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="9184a-347">필드에 `Serialize` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-347">Applying the `Serialize` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="9184a-348">포함 형식이 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-348">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="9184a-349">필드의 형식이 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-349">The type of the field is marked with the `Serialize` policy.</span></span>

#### <a name="the-effect-of-xmlserializer-datacontractserializer-and-datacontractjsonserializer-policies"></a><span data-ttu-id="9184a-350">XmlSerializer, DataContractSerializer 및 DataContractJsonSerializer 정책의 영향</span><span class="sxs-lookup"><span data-stu-id="9184a-350">The effect of XmlSerializer, DataContractSerializer, and DataContractJsonSerializer policies</span></span>

<span data-ttu-id="9184a-351">리플렉션 기반 serializer를 위한 `Serialize` 정책과 달리 <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>및 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 정책은 .NET 네이티브 도구 체인에 알려진 일련의 직렬 변환기를 사용 하도록 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-351">Unlike the `Serialize` policy, which is intended for reflection-based serializers, the <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>, and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> policies are used to enable a set of serializers that are known to the .NET Native tool chain.</span></span> <span data-ttu-id="9184a-352">이러한 serializer는 리플렉션을 사용하여 구현되지 않으며 런타임에 serialize할 수 있는 형식 집합은 리플렉션 가능한 형식과 비슷한 방식으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-352">These serializers are not implemented by using reflection, but the set of types that can be serialized at run time is determined in a similar manner as types that are reflectable.</span></span>

<span data-ttu-id="9184a-353">이러한 정책 중 하나를 형식에 적용하면 일치하는 serializer를 사용하여 형식을 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-353">Applying one of these policies to a type enables the type to be serialized with the matching serializer.</span></span> <span data-ttu-id="9184a-354">또한 serialization 엔진이 serialization을 수행해야 한다고 정적으로 확인할 수 있는 모든 형식도 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-354">Also, any types that the serialization engine can statically determine as needing serialization will also be serializable.</span></span>

<span data-ttu-id="9184a-355">이러한 정책은 메서드 또는 필드에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9184a-355">These policies have no effect on methods or fields.</span></span>

<span data-ttu-id="9184a-356">자세한 내용은 [Windows 스토어 앱을 .NET 네이티브로 마이그레이션](migrating-your-windows-store-app-to-net-native.md)에서 “직렬 변환기의 차이점” 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9184a-356">For more information, see the "Differences in Serializers" section in [Migrating Your Windows Store App to .NET Native](migrating-your-windows-store-app-to-net-native.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9184a-357">참조</span><span class="sxs-lookup"><span data-stu-id="9184a-357">See also</span></span>

- [<span data-ttu-id="9184a-358">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="9184a-358">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="9184a-359">리플렉션 및 .NET 네이티브</span><span class="sxs-lookup"><span data-stu-id="9184a-359">Reflection and .NET Native</span></span>](reflection-and-net-native.md)

---
title: COM 상호 운용성을 위한 .NET 형식의 정규화
description: 이 문서에서는 COM interop을 위해 COM 애플리케이션에 .NET 어셈블리의 형식을 노출하는 데 도움이 되는 지침을 제공합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, qualifying .NET types
- qualifying .NET types for interoperation
- interoperation with unmanaged code, qualifying .NET types
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
ms.openlocfilehash: 5b122befffbcad39258393462c75ac20431d9136
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420502"
---
# <a name="qualifying-net-types-for-com-interoperation"></a><span data-ttu-id="6d70f-103">COM 상호 운용성을 위한 .NET 형식의 정규화</span><span class="sxs-lookup"><span data-stu-id="6d70f-103">Qualifying .NET Types for COM Interoperation</span></span>
<span data-ttu-id="6d70f-104">어셈블리에서 형식을 COM 애플리케이션으로 노출하려는 경우 디자인 타임에 COM interop의 요구 사항을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="6d70f-104">If you intend to expose types in an assembly to COM applications, consider the requirements of COM interop at design time.</span></span> <span data-ttu-id="6d70f-105">다음 지침을 준수하면 관리되는 형식(클래스, 인터페이스, 구조체 및 열거형)이 COM 형식과 원활하게 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-105">Managed types (class, interface, structure, and enumeration) seamlessly integrate with COM types when you adhere to the following guidelines:</span></span>  
  
- <span data-ttu-id="6d70f-106">클래스에서 인터페이스를 명시적으로 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-106">Classes should implement interfaces explicitly.</span></span>  
  
     <span data-ttu-id="6d70f-107">COM interop에서 클래스의 모든 멤버와 기본 클래스의 멤버를 포함하는 인터페이스를 자동으로 생성하는 메커니즘을 제공하지만 명시적 인터페이스를 제공하는 것이 훨씬 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-107">Although COM interop provides a mechanism to automatically generate an interface containing all members of the class and the members of its base class, it is far better to provide explicit interfaces.</span></span> <span data-ttu-id="6d70f-108">자동으로 생성된 인터페이스는 클래스 인터페이스라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-108">The automatically generated interface is called the class interface.</span></span> <span data-ttu-id="6d70f-109">지침은 [클래스 인터페이스 소개](com-callable-wrapper.md#introducing-the-class-interface)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d70f-109">For guidelines, see [Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface).</span></span>  
  
     <span data-ttu-id="6d70f-110">IDL(Interface Definition Language) 또는 이와 동등한 사항을 사용할 필요 없이 Visual Basic, C# 및 C++를 사용하여 코드에 인터페이스 정의를 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-110">You can use Visual Basic, C#, and C++ to incorporate interface definitions in your code, instead of having to use Interface Definition Language (IDL) or its equivalent.</span></span> <span data-ttu-id="6d70f-111">구문에 대한 세부 정보는 언어 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d70f-111">For syntax details, see your language documentation.</span></span>  
  
- <span data-ttu-id="6d70f-112">관리되는 형식은 public이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-112">Managed types must be public.</span></span>  
  
     <span data-ttu-id="6d70f-113">어셈블리의 public 형식만 등록하고 형식 라이브러리로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-113">Only public types in an assembly are registered and exported to the type library.</span></span> <span data-ttu-id="6d70f-114">결과적으로 public 형식만 COM에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-114">As a result, only public types are visible to COM.</span></span>  
  
     <span data-ttu-id="6d70f-115">관리되는 형식은 COM에 노출되지 않을 수 있는 기타 관리 코드에 기능을 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-115">Managed types expose features to other managed code that might not be exposed to COM.</span></span> <span data-ttu-id="6d70f-116">예를 들어 매개 변수화된 생성자, 정적 메서드 및 상수 필드는 COM 클라이언트에 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-116">For instance, parameterized constructors, static methods, and constant fields are not exposed to COM clients.</span></span> <span data-ttu-id="6d70f-117">또한 런타임 시 데이터를 형식에 대해 마샬링할 때 데이터가 복사되거나 변환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-117">Further, as the runtime marshals data in and out of a type, the data might be copied or transformed.</span></span>  
  
- <span data-ttu-id="6d70f-118">메서드, 속성, 필드 및 이벤트는 public이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-118">Methods, properties, fields, and events must be public.</span></span>  
  
     <span data-ttu-id="6d70f-119">public 형식의 멤버를 COM에 표시하려는 경우 해당 멤버도 public이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-119">Members of public types must also be public if they are to be visible to COM.</span></span> <span data-ttu-id="6d70f-120"><xref:System.Runtime.InteropServices.ComVisibleAttribute>를 적용하여 어셈블리의 가시성, public 형식 또는 public 형식의 공용 멤버를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-120">You can restrict the visibility of an assembly, a public type, or public members of a public type by applying the <xref:System.Runtime.InteropServices.ComVisibleAttribute>.</span></span> <span data-ttu-id="6d70f-121">기본적으로 모든 public 형식 및 멤버만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-121">By default, all public types and members are visible.</span></span>  
  
- <span data-ttu-id="6d70f-122">형식에는 COM에서 활성화될 public 매개 변수가 없는 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-122">Types must have a public parameterless constructor to be activated from COM.</span></span>  
  
     <span data-ttu-id="6d70f-123">관리되는 public 형식만 COM에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-123">Managed, public types are visible to COM.</span></span> <span data-ttu-id="6d70f-124">그러나 public 매개 변수가 없는 생성자(인수 없는 생성자)가 없으면 COM 클라이언트에서 형식을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-124">However, without a public parameterless constructor (a constructor with no arguments), COM clients cannot create the type.</span></span> <span data-ttu-id="6d70f-125">다른 방법으로 활성화된 경우에도 COM 클라이언트에서 여전히 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-125">COM clients can still use the type if it is activated by some other means.</span></span>  
  
- <span data-ttu-id="6d70f-126">형식은 추상일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-126">Types cannot be abstract.</span></span>  
  
     <span data-ttu-id="6d70f-127">COM 클라이언트와 .NET 클라이언트 모두 추상 형식을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-127">Neither COM clients nor .NET clients can create abstract types.</span></span>  
  
 <span data-ttu-id="6d70f-128">COM으로 내보낼 때 관리되는 형식의 상속 계층 구조가 평면화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-128">When exported to COM, the inheritance hierarchy of a managed type is flattened.</span></span> <span data-ttu-id="6d70f-129">관리되는 환경과 관리되지 않는 환경에서는 버전 관리도 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-129">Versioning also differs between managed and unmanaged environments.</span></span> <span data-ttu-id="6d70f-130">COM에 노출된 형식에는 관리되는 다른 형식과 동일한 버전 관리 특성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d70f-130">Types exposed to COM do not have the same versioning characteristics as other managed types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d70f-131">참조</span><span class="sxs-lookup"><span data-stu-id="6d70f-131">See also</span></span>

- <xref:System.Runtime.InteropServices.ComVisibleAttribute>
- [<span data-ttu-id="6d70f-132">.NET Framework 구성 요소를 COM에 노출</span><span class="sxs-lookup"><span data-stu-id="6d70f-132">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="6d70f-133">클래스 인터페이스 소개</span><span class="sxs-lookup"><span data-stu-id="6d70f-133">Introducing the class interface</span></span>](com-callable-wrapper.md#introducing-the-class-interface)
- [<span data-ttu-id="6d70f-134">Interop 특성 적용</span><span class="sxs-lookup"><span data-stu-id="6d70f-134">Applying Interop Attributes</span></span>](../../../docs/standard/native-interop/apply-interop-attributes.md)
- [<span data-ttu-id="6d70f-135">COM용 .NET Framework 어셈블리 패키징</span><span class="sxs-lookup"><span data-stu-id="6d70f-135">Packaging a .NET Framework Assembly for COM</span></span>](../../../docs/framework/interop/packaging-an-assembly-for-com.md)

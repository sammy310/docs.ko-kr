---
title: 비관리 코드와의 상호 운용
ms.date: 01/17/2018
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
ms.openlocfilehash: 12183f390a5178f038c6dd2122a72a33e31ae0ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457962"
---
# <a name="interoperating-with-unmanaged-code"></a><span data-ttu-id="97fa6-102">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="97fa6-102">Interoperating with unmanaged code</span></span>

<span data-ttu-id="97fa6-103">.NET Framework를 기반으로 COM 구성 요소, COM+ 서비스, 외부 형식 라이브러리 및 여러 가지 운영 체제 서비스와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-103">The .NET Framework promotes interaction with COM components, COM+ services, external type libraries, and many operating system services.</span></span> <span data-ttu-id="97fa6-104">관리 개체 모델과 관리되지 않는 개체 모델 간에는 데이터 형식, 메서드 시그니처 및 오류 처리 메커니즘이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-104">Data types, method signatures, and error-handling mechanisms vary between managed and unmanaged object models.</span></span> <span data-ttu-id="97fa6-105">.NET Framework 구성 요소와 비관리 코드 간에 상호 운용을 간소화하고 마이그레이션 경로를 줄이기 위해 공용 언어 런타임은 클라이언트 및 서버에서 둘 다 이러한 개체 모델의 차이점을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-105">To simplify interoperation between .NET Framework components and unmanaged code and to ease the migration path, the common language runtime conceals from both clients and servers the differences in these object models.</span></span>

<span data-ttu-id="97fa6-106">런타임 제어를 기반으로 실행되는 코드를 관리 코드라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-106">Code that executes under the control of the runtime is called managed code.</span></span> <span data-ttu-id="97fa6-107">이와 달리 런타임 외부에서 실행되는 코드를 비관리 코드라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-107">Conversely, code that runs outside the runtime is called unmanaged code.</span></span> <span data-ttu-id="97fa6-108">비관리 코드로는 COM 구성 요소, ActiveX 인터페이스, Windows API 함수 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-108">COM components, ActiveX interfaces, and Windows API functions are examples of unmanaged code.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="97fa6-109">단원 내용</span><span class="sxs-lookup"><span data-stu-id="97fa6-109">In this section</span></span>

[<span data-ttu-id="97fa6-110">.NET Framework에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="97fa6-110">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)  
<span data-ttu-id="97fa6-111">.NET Framework 애플리케이션에서 COM 구성 요소를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-111">Describes how to use COM components from .NET Framework applications.</span></span>

[<span data-ttu-id="97fa6-112">.NET Framework 구성 요소를 COM에 노출</span><span class="sxs-lookup"><span data-stu-id="97fa6-112">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)  
<span data-ttu-id="97fa6-113">COM 애플리케이션에서 .NET Framework 구성 요소를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-113">Describes how to use .NET Framework components from COM applications.</span></span>

[<span data-ttu-id="97fa6-114">관리되지 않는 DLL 함수 사용</span><span class="sxs-lookup"><span data-stu-id="97fa6-114">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
<span data-ttu-id="97fa6-115">플랫폼 호출을 사용하여 관리되지 않는 DLL 함수를 호출하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-115">Describes how to call unmanaged DLL functions using platform invoke.</span></span>

[<span data-ttu-id="97fa6-116">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="97fa6-116">Interop Marshaling</span></span>](interop-marshaling.md)  
<span data-ttu-id="97fa6-117">COM interop 및 플랫폼 호출에 대한 마샬링을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-117">Describes marshaling for COM interop and platform invoke.</span></span>

[<span data-ttu-id="97fa6-118">방법: HRESULT 및 예외 매핑</span><span class="sxs-lookup"><span data-stu-id="97fa6-118">How to: Map HRESULTs and Exceptions</span></span>](how-to-map-hresults-and-exceptions.md)  
<span data-ttu-id="97fa6-119">실행과 HRESULT 간 매핑을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-119">Describes the mapping between exceptions and HRESULTs.</span></span>

[<span data-ttu-id="97fa6-120">동일 형식 및 포함된 Interop 형식</span><span class="sxs-lookup"><span data-stu-id="97fa6-120">Type Equivalence and Embedded Interop Types</span></span>](type-equivalence-and-embedded-interop-types.md)  
<span data-ttu-id="97fa6-121">COM 형식에 대한 형식 정보가 어셈블리에 포함되는 방식과 공용 언어 런타임에서 포함된 COM 형식이 동일한지 결정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-121">Describes how type information for COM types is embedded in assemblies, and how the common language runtime determines the equivalence of embedded COM types.</span></span>

[<span data-ttu-id="97fa6-122">방법: Tlbimp.exe를 사용하여 주 Interop 어셈블리 생성</span><span class="sxs-lookup"><span data-stu-id="97fa6-122">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
<span data-ttu-id="97fa6-123">*Tlbimp.exe*(형식 라이브러리 가져오기)를 사용하여 주 interop 어셈블리를 생성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-123">Describes how to produce primary interop assemblies using *Tlbimp.exe* (Type Library Importer).</span></span>

[<span data-ttu-id="97fa6-124">방법: 주 Interop 어셈블리 등록</span><span class="sxs-lookup"><span data-stu-id="97fa6-124">How to: Register Primary Interop Assemblies</span></span>](how-to-register-primary-interop-assemblies.md)  
<span data-ttu-id="97fa6-125">주 interop 어셈블리를 프로젝트에서 참조할 수 있도록 등록하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-125">Describes how to register the primary interop assemblies before you can reference them in your projects.</span></span>

[<span data-ttu-id="97fa6-126">등록이 필요 없는 COM interop</span><span class="sxs-lookup"><span data-stu-id="97fa6-126">Registration-Free COM Interop</span></span>](registration-free-com-interop.md)  
<span data-ttu-id="97fa6-127">COM interop에서 Windows 레지스트리를 사용하지 않고 구성 요소를 활성화하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-127">Describes how COM interop can activate components without using the Windows registry.</span></span>

[<span data-ttu-id="97fa6-128">방법: 등록이 필요 없는 활성화를 위한 .NET Framework 기반 COM 구성 요소 구성</span><span class="sxs-lookup"><span data-stu-id="97fa6-128">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>](configure-net-framework-based-com-components-for-reg.md)  
<span data-ttu-id="97fa6-129">애플리케이션 매니페스트를 만드는 방법과 구성 요소 매니페스트를 만들고 포함하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-129">Describes how to create an application manifest and how to create and embed a component manifest.</span></span>

## <a name="related-sections"></a><span data-ttu-id="97fa6-130">관련 단원</span><span class="sxs-lookup"><span data-stu-id="97fa6-130">Related sections</span></span>

[<span data-ttu-id="97fa6-131">COM 래퍼</span><span class="sxs-lookup"><span data-stu-id="97fa6-131">COM Wrappers</span></span>](../../standard/native-interop/com-wrappers.md)  
<span data-ttu-id="97fa6-132">COM interop에서 제공하는 래퍼에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97fa6-132">Describes the wrappers provided by COM interop.</span></span>

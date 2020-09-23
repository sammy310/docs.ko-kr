---
title: COM Interop
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, COM interop
- COM interop [Visual Basic], in Visual Basic
ms.assetid: 3ffd1bdf-1b8d-47f5-87eb-75b659f64294
ms.openlocfilehash: 66762d4551e458b36b70fb0831bf17ade70aa8cb
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91083230"
---
# <a name="com-interop-visual-basic"></a><span data-ttu-id="293ea-102">COM Interop(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="293ea-102">COM Interop (Visual Basic)</span></span>

<span data-ttu-id="293ea-103">COM(구성 요소 개체 모델)을 통해 개체는 기능을 다른 구성 요소에 노출하고 애플리케이션을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-103">The Component Object Model (COM) allows an object to expose its functionality to other components and to host applications.</span></span> <span data-ttu-id="293ea-104">오늘날 대부분의 소프트웨어에는 COM 개체가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-104">Most of today's software includes COM objects.</span></span> <span data-ttu-id="293ea-105">새 애플리케이션에는 .NET 어셈블리가 제일 나은 선택이지만 때로는 COM 개체를 채택해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-105">Although .NET assemblies are the best choice for new applications, you may at times need to employ COM objects.</span></span> <span data-ttu-id="293ea-106">이 섹션에서는 Visual Basic로 COM 개체를 만들고 사용 하는 것과 관련 된 몇 가지 문제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-106">This section covers some of the issues associated with creating and using COM objects with Visual Basic.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="293ea-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="293ea-107">In This Section</span></span>  

 [<span data-ttu-id="293ea-108">COM Interop 소개</span><span class="sxs-lookup"><span data-stu-id="293ea-108">Introduction to COM Interop</span></span>](introduction-to-com-interop.md)  
 <span data-ttu-id="293ea-109">COM 상호 운용성의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-109">Provides an overview of COM interoperability.</span></span>  
  
 [<span data-ttu-id="293ea-110">방법: Visual Basic에서 COM 개체 참조</span><span class="sxs-lookup"><span data-stu-id="293ea-110">How to: Reference COM Objects from Visual Basic</span></span>](how-to-reference-com-objects.md)  
 <span data-ttu-id="293ea-111">형식 라이브러리가 포함된 COM 개체에 참조를 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-111">Covers how to add references to COM objects that have type libraries.</span></span>  
  
 [<span data-ttu-id="293ea-112">방법: ActiveX 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="293ea-112">How to: Work with ActiveX Controls</span></span>](how-to-work-with-activex-controls.md)  
 <span data-ttu-id="293ea-113">기존 ActiveX 컨트롤을 사용 하 여 Visual Studio 도구 상자에 기능을 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-113">Demonstrates how to use existing ActiveX controls to add features to the Visual Studio Toolbox.</span></span>  
  
 [<span data-ttu-id="293ea-114">연습: Windows API 호출</span><span class="sxs-lookup"><span data-stu-id="293ea-114">Walkthrough: Calling Windows APIs</span></span>](walkthrough-calling-windows-apis.md)  
 <span data-ttu-id="293ea-115">Windows 운영 체제에 포함된 API를 호출하는 프로세스를 단계별로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-115">Steps you through the process of calling the APIs that are part of the Windows operating system.</span></span>  
  
 [<span data-ttu-id="293ea-116">방법: Windows API 호출</span><span class="sxs-lookup"><span data-stu-id="293ea-116">How to: Call Windows APIs</span></span>](how-to-call-windows-apis.md)  
 <span data-ttu-id="293ea-117">User32.dll에서 `MessageBox` 함수를 정의 및 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-117">Demonstrates how to define and call the `MessageBox` function in User32.dll.</span></span>  
  
 [<span data-ttu-id="293ea-118">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="293ea-118">How to: Call a Windows Function that Takes Unsigned Types</span></span>](how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 <span data-ttu-id="293ea-119">서명되지 않은 형식의 매개 변수가 있는 Windows 함수를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-119">Demonstrates how to call a Windows function that has a parameter of an unsigned type.</span></span>  
  
 [<span data-ttu-id="293ea-120">연습: Visual Basic을 사용하여 COM 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="293ea-120">Walkthrough: Creating COM Objects with Visual Basic</span></span>](walkthrough-creating-com-objects.md)  
 <span data-ttu-id="293ea-121">COM 클래스 템플릿을 사용하거나 사용하지 않고 COM 개체를 만드는 프로세스를 단계별로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-121">Steps you through the process of creating COM objects with and without the COM class template.</span></span>  
  
 [<span data-ttu-id="293ea-122">상호 운용성 문제 해결</span><span class="sxs-lookup"><span data-stu-id="293ea-122">Troubleshooting Interoperability</span></span>](troubleshooting-interoperability.md)  
 <span data-ttu-id="293ea-123">COM을 사용할 경우 발생할 수 있는 일부 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-123">Covers some of the problems you may encounter when using COM.</span></span>  
  
 [<span data-ttu-id="293ea-124">.NET Framework 애플리케이션의 COM 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="293ea-124">COM Interoperability in .NET Framework Applications</span></span>](com-interoperability-in-net-framework-applications.md)  
 <span data-ttu-id="293ea-125">같은 애플리케이션에서 COM 개체 및 .NET Framework 개체를 사용하는 방법의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-125">Provides an overview of how to use COM objects and .NET Framework objects in the same application.</span></span>  
  
 [<span data-ttu-id="293ea-126">연습: COM 개체를 사용한 상속 구현</span><span class="sxs-lookup"><span data-stu-id="293ea-126">Walkthrough: Implementing Inheritance with COM Objects</span></span>](walkthrough-implementing-inheritance-with-com-objects.md)  
 <span data-ttu-id="293ea-127">기존 COM 개체를 새 개체의 기반으로 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-127">Describes using existing COM objects as the basis for new objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="293ea-128">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="293ea-128">Related Sections</span></span>  

 [<span data-ttu-id="293ea-129">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="293ea-129">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="293ea-130">공용 언어 런타임에서 제공하는 상호 운용성 서비스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-130">Describes interoperability services provided by the common language runtime.</span></span>  
  
 [<span data-ttu-id="293ea-131">.NET Framework에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="293ea-131">Exposing COM Components to the .NET Framework</span></span>](../../../framework/interop/exposing-com-components.md)  
 <span data-ttu-id="293ea-132">COM interop를 통해 COM 형식을 호출하는 프로세스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-132">Describes the process of calling COM types through COM interop.</span></span>  
  
 [<span data-ttu-id="293ea-133">.NET Framework 구성 요소를 COM에 노출</span><span class="sxs-lookup"><span data-stu-id="293ea-133">Exposing .NET Framework Components to COM</span></span>](../../../framework/interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="293ea-134">COM에서 관리되는 형식의 준비 및 사용을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-134">Describes the preparation and use of managed types from COM.</span></span>  
  
 [<span data-ttu-id="293ea-135">Interop 특성 적용</span><span class="sxs-lookup"><span data-stu-id="293ea-135">Applying Interop Attributes</span></span>](../../../standard/native-interop/apply-interop-attributes.md)  
 <span data-ttu-id="293ea-136">비관리 코드를 사용할 때 사용할 수 있는 특성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="293ea-136">Covers attributes you can use when working with unmanaged code.</span></span>

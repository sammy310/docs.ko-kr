---
description: '자세한 정보: COM Interop (Visual Basic)'
title: COM Interop
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, COM interop
- COM interop [Visual Basic], in Visual Basic
ms.assetid: 3ffd1bdf-1b8d-47f5-87eb-75b659f64294
ms.openlocfilehash: 02ce21c6175f76bca17ae6ab57aa1569800167f4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100460711"
---
# <a name="com-interop-visual-basic"></a><span data-ttu-id="ab32e-103">COM Interop(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab32e-103">COM Interop (Visual Basic)</span></span>

<span data-ttu-id="ab32e-104">COM(구성 요소 개체 모델)을 통해 개체는 기능을 다른 구성 요소에 노출하고 애플리케이션을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-104">The Component Object Model (COM) allows an object to expose its functionality to other components and to host applications.</span></span> <span data-ttu-id="ab32e-105">오늘날 대부분의 소프트웨어에는 COM 개체가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-105">Most of today's software includes COM objects.</span></span> <span data-ttu-id="ab32e-106">새 애플리케이션에는 .NET 어셈블리가 제일 나은 선택이지만 때로는 COM 개체를 채택해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-106">Although .NET assemblies are the best choice for new applications, you may at times need to employ COM objects.</span></span> <span data-ttu-id="ab32e-107">이 섹션에서는 Visual Basic로 COM 개체를 만들고 사용 하는 것과 관련 된 몇 가지 문제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-107">This section covers some of the issues associated with creating and using COM objects with Visual Basic.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ab32e-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ab32e-108">In This Section</span></span>  

 [<span data-ttu-id="ab32e-109">COM Interop 소개</span><span class="sxs-lookup"><span data-stu-id="ab32e-109">Introduction to COM Interop</span></span>](introduction-to-com-interop.md)  
 <span data-ttu-id="ab32e-110">COM 상호 운용성의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-110">Provides an overview of COM interoperability.</span></span>  
  
 [<span data-ttu-id="ab32e-111">방법: Visual Basic에서 COM 개체 참조</span><span class="sxs-lookup"><span data-stu-id="ab32e-111">How to: Reference COM Objects from Visual Basic</span></span>](how-to-reference-com-objects.md)  
 <span data-ttu-id="ab32e-112">형식 라이브러리가 포함된 COM 개체에 참조를 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-112">Covers how to add references to COM objects that have type libraries.</span></span>  
  
 [<span data-ttu-id="ab32e-113">방법: ActiveX 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="ab32e-113">How to: Work with ActiveX Controls</span></span>](how-to-work-with-activex-controls.md)  
 <span data-ttu-id="ab32e-114">기존 ActiveX 컨트롤을 사용 하 여 Visual Studio 도구 상자에 기능을 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-114">Demonstrates how to use existing ActiveX controls to add features to the Visual Studio Toolbox.</span></span>  
  
 [<span data-ttu-id="ab32e-115">연습: Windows API 호출</span><span class="sxs-lookup"><span data-stu-id="ab32e-115">Walkthrough: Calling Windows APIs</span></span>](walkthrough-calling-windows-apis.md)  
 <span data-ttu-id="ab32e-116">Windows 운영 체제에 포함된 API를 호출하는 프로세스를 단계별로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-116">Steps you through the process of calling the APIs that are part of the Windows operating system.</span></span>  
  
 [<span data-ttu-id="ab32e-117">방법: Windows API 호출</span><span class="sxs-lookup"><span data-stu-id="ab32e-117">How to: Call Windows APIs</span></span>](how-to-call-windows-apis.md)  
 <span data-ttu-id="ab32e-118">User32.dll에서 `MessageBox` 함수를 정의 및 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-118">Demonstrates how to define and call the `MessageBox` function in User32.dll.</span></span>  
  
 [<span data-ttu-id="ab32e-119">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="ab32e-119">How to: Call a Windows Function that Takes Unsigned Types</span></span>](how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 <span data-ttu-id="ab32e-120">서명되지 않은 형식의 매개 변수가 있는 Windows 함수를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-120">Demonstrates how to call a Windows function that has a parameter of an unsigned type.</span></span>  
  
 [<span data-ttu-id="ab32e-121">연습: Visual Basic을 사용하여 COM 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="ab32e-121">Walkthrough: Creating COM Objects with Visual Basic</span></span>](walkthrough-creating-com-objects.md)  
 <span data-ttu-id="ab32e-122">COM 클래스 템플릿을 사용하거나 사용하지 않고 COM 개체를 만드는 프로세스를 단계별로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-122">Steps you through the process of creating COM objects with and without the COM class template.</span></span>  
  
 [<span data-ttu-id="ab32e-123">상호 운용성 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ab32e-123">Troubleshooting Interoperability</span></span>](troubleshooting-interoperability.md)  
 <span data-ttu-id="ab32e-124">COM을 사용할 경우 발생할 수 있는 일부 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-124">Covers some of the problems you may encounter when using COM.</span></span>  
  
 [<span data-ttu-id="ab32e-125">.NET Framework 애플리케이션의 COM 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="ab32e-125">COM Interoperability in .NET Framework Applications</span></span>](com-interoperability-in-net-framework-applications.md)  
 <span data-ttu-id="ab32e-126">같은 애플리케이션에서 COM 개체 및 .NET Framework 개체를 사용하는 방법의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-126">Provides an overview of how to use COM objects and .NET Framework objects in the same application.</span></span>  
  
 [<span data-ttu-id="ab32e-127">연습: COM 개체를 사용한 상속 구현</span><span class="sxs-lookup"><span data-stu-id="ab32e-127">Walkthrough: Implementing Inheritance with COM Objects</span></span>](walkthrough-implementing-inheritance-with-com-objects.md)  
 <span data-ttu-id="ab32e-128">기존 COM 개체를 새 개체의 기반으로 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-128">Describes using existing COM objects as the basis for new objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ab32e-129">관련 단원</span><span class="sxs-lookup"><span data-stu-id="ab32e-129">Related Sections</span></span>  

 [<span data-ttu-id="ab32e-130">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="ab32e-130">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="ab32e-131">공용 언어 런타임에서 제공하는 상호 운용성 서비스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-131">Describes interoperability services provided by the common language runtime.</span></span>  
  
 [<span data-ttu-id="ab32e-132">.NET Framework에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="ab32e-132">Exposing COM Components to the .NET Framework</span></span>](../../../framework/interop/exposing-com-components.md)  
 <span data-ttu-id="ab32e-133">COM interop를 통해 COM 형식을 호출하는 프로세스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-133">Describes the process of calling COM types through COM interop.</span></span>  
  
 [<span data-ttu-id="ab32e-134">.NET Framework 구성 요소를 COM에 노출</span><span class="sxs-lookup"><span data-stu-id="ab32e-134">Exposing .NET Framework Components to COM</span></span>](../../../framework/interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="ab32e-135">COM에서 관리되는 형식의 준비 및 사용을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-135">Describes the preparation and use of managed types from COM.</span></span>  
  
 [<span data-ttu-id="ab32e-136">Interop 특성 적용</span><span class="sxs-lookup"><span data-stu-id="ab32e-136">Applying Interop Attributes</span></span>](../../../standard/native-interop/apply-interop-attributes.md)  
 <span data-ttu-id="ab32e-137">비관리 코드를 사용할 때 사용할 수 있는 특성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab32e-137">Covers attributes you can use when working with unmanaged code.</span></span>

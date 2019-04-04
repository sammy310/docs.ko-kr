---
title: .NET Framework 애플리케이션의 COM 상호 운용성(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: 6e8b4eba40cc1872cb289ca120679bb951f2652a
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920807"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="d6c9b-102">.NET Framework 애플리케이션의 COM 상호 운용성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6c9b-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>

<span data-ttu-id="d6c9b-103">동일한 응용 프로그램에서 COM 개체 및.NET Framework 개체를 사용 하려는 경우에 개체가 메모리에 존재 하는 방법의 차이 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c9b-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="d6c9b-104">.NET Framework 개체를 관리 되는 메모리에 위치한-공용 언어 런타임에 의해 제어 하는 메모리-필요에 따라 런타임에 의해 이동 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6c9b-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="d6c9b-105">COM 개체는 관리 되지 않는 메모리에 있으며 다른 메모리 위치로 이동 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6c9b-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> <span data-ttu-id="d6c9b-106">Visual Studio 및 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 이러한 상호 작용을 제어 하는 도구 관리 코드와 비관리 구성 요소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c9b-106">Visual Studio and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="d6c9b-107">관리 코드에 대 한 자세한 내용은 참조 하세요. [공용 언어 런타임](../../../standard/clr.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c9b-107">For more information about managed code, see [Common Language Runtime](../../../standard/clr.md).</span></span>

<span data-ttu-id="d6c9b-108">.NET 응용 프로그램에서 COM 개체를 사용 하는 것 외에도 수도 있습니다 Visual Basic COM. 통해 비관리 코드에서 액세스할 수 있는 개체를 개발 하는 데</span><span class="sxs-lookup"><span data-stu-id="d6c9b-108">In addition to using COM objects in .NET applications, you may also want to use Visual Basic to develop objects accessible from unmanaged code through COM.</span></span>

<span data-ttu-id="d6c9b-109">이 페이지의 링크 COM 및.NET Framework 개체 간의 상호 작용에 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c9b-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>

## <a name="related-sections"></a><span data-ttu-id="d6c9b-110">관련 단원</span><span class="sxs-lookup"><span data-stu-id="d6c9b-110">Related sections</span></span>

| | |
|---------|---------|
| [<span data-ttu-id="d6c9b-111">COM Interop</span><span class="sxs-lookup"><span data-stu-id="d6c9b-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md) | <span data-ttu-id="d6c9b-112">Visual basic에서 COM 개체, ActiveX 컨트롤, Win32 Dll, 관리 되는 개체 및 COM 개체의 상속을 포함 하 여 COM 상호 운용성을 다루는 항목에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c9b-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span> |
| [<span data-ttu-id="d6c9b-113">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="d6c9b-113">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md) | <span data-ttu-id="d6c9b-114">간단 하 게 관리 및 비관리 코드 간의 상호 작용 문제 중 일부를 설명 하 고 추가 연구에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c9b-114">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span> |
| [<span data-ttu-id="d6c9b-115">COM 래퍼</span><span class="sxs-lookup"><span data-stu-id="d6c9b-115">COM Wrappers</span></span>](../../../framework/interop/com-wrappers.md) | <span data-ttu-id="d6c9b-116">COM 메서드를 호출 하는 관리 되는 코드를 허용 하는 런타임 호출 가능 래퍼 및 COM 클라이언트가.NET 개체 메서드를 호출 하도록 허용 하는 COM 호출 가능 래퍼에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c9b-116">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span> |
| [<span data-ttu-id="d6c9b-117">고급 수준의 COM 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="d6c9b-117">Advanced COM Interoperability</span></span>](../../../framework/interop/index.md) | <span data-ttu-id="d6c9b-118">래퍼, 예외, 상속, 스레딩, 이벤트, 변환 및 마샬링 관련 하 여 COM 상호 운용성을 다루는 항목에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c9b-118">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span> |
| [<span data-ttu-id="d6c9b-119">Tlbimp.exe(형식 라이브러리 가져오기)</span><span class="sxs-lookup"><span data-stu-id="d6c9b-119">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md) | <span data-ttu-id="d6c9b-120">COM 형식 라이브러리에 있는 형식 정의 공용 언어 런타임 어셈블리의 동등한 정의로 변환 하 여 도구를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c9b-120">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span> |
---
title: .NET Framework 애플리케이션의 COM 상호 운용성
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET Framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: c3567464616d3b0b3f91ff57e8a169aca046c866
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452294"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="e0246-102">.NET Framework 애플리케이션의 COM 상호 운용성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0246-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>

<span data-ttu-id="e0246-103">COM 개체를 사용 하 고 동일한 응용 프로그램에서 개체를 .NET Framework 하려면 개체가 메모리에 존재 하는 방식의 차이를 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0246-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="e0246-104">.NET Framework 개체는 관리 되는 메모리 (공용 언어 런타임에 의해 제어 되는 메모리)에 있으며 필요에 따라 런타임에 의해 이동 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0246-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="e0246-105">COM 개체는 관리 되지 않는 메모리에 있으며 다른 메모리 위치로 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0246-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> <span data-ttu-id="e0246-106">Visual Studio 및 .NET Framework는 이러한 관리 되는 구성 요소와 관리 되지 않는 구성 요소의 상호 작용을 제어 하는 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0246-106">Visual Studio and the .NET Framework provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="e0246-107">관리 코드에 대 한 자세한 내용은 [공용 언어 런타임](../../../standard/clr.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0246-107">For more information about managed code, see [Common Language Runtime](../../../standard/clr.md).</span></span>

<span data-ttu-id="e0246-108">.NET 응용 프로그램에서 COM 개체를 사용 하는 것 외에도 Visual Basic를 사용 하 여 COM을 통해 비관리 코드에서 액세스할 수 있는 개체를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0246-108">In addition to using COM objects in .NET applications, you may also want to use Visual Basic to develop objects accessible from unmanaged code through COM.</span></span>

<span data-ttu-id="e0246-109">이 페이지의 링크는 COM과 .NET Framework 개체 간의 상호 작용에 대 한 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0246-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>

## <a name="related-sections"></a><span data-ttu-id="e0246-110">관련 단원</span><span class="sxs-lookup"><span data-stu-id="e0246-110">Related sections</span></span>

| | |
|---------|---------|
| [<span data-ttu-id="e0246-111">COM Interop</span><span class="sxs-lookup"><span data-stu-id="e0246-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md) | <span data-ttu-id="e0246-112">Com 개체, ActiveX 컨트롤, Win32 Dll, 관리 되는 개체 및 COM 개체의 상속을 비롯 하 여 Visual Basic의 COM 상호 운용성을 다루는 항목에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0246-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span> |
| [<span data-ttu-id="e0246-113">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="e0246-113">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md) | <span data-ttu-id="e0246-114">관리 코드와 비관리 코드 간의 상호 작용 문제 중 일부에 대해 간략하게 설명 하 고 추가 조사를 위한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0246-114">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span> |
| [<span data-ttu-id="e0246-115">COM 래퍼</span><span class="sxs-lookup"><span data-stu-id="e0246-115">COM Wrappers</span></span>](../../../standard/native-interop/com-wrappers.md) | <span data-ttu-id="e0246-116">관리 코드에서 COM 메서드를 호출할 수 있도록 하는 런타임 호출 가능 래퍼와 com 클라이언트에서 .NET 개체 메서드를 호출할 수 있도록 하는 COM 호출 가능 래퍼에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0246-116">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span> |
| [<span data-ttu-id="e0246-117">고급 COM 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="e0246-117">Advanced COM Interoperability</span></span>](../../../framework/interop/index.md) | <span data-ttu-id="e0246-118">래퍼, 예외, 상속, 스레딩, 이벤트, 변환 및 마샬링과 관련 하 여 COM 상호 운용성을 다루는 항목의 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0246-118">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span> |
| [<span data-ttu-id="e0246-119">Tlbimp.exe(형식 라이브러리 가져오기)</span><span class="sxs-lookup"><span data-stu-id="e0246-119">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md) | <span data-ttu-id="e0246-120">COM 형식 라이브러리에 있는 형식 정의를 공용 언어 런타임 어셈블리의 동등한 정의로 변환 하는 데 사용할 수 있는 도구에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0246-120">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span> |

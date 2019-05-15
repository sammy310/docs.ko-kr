---
title: COM Interop를 사용하여 데이터 마샬링
ms.date: 09/07/2017
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 807e514fac7d33cdacac3a48a37c7aa8dd92ef9c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648637"
---
# <a name="marshaling-data-with-com-interop"></a><span data-ttu-id="f4415-102">COM Interop를 사용하여 데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="f4415-102">Marshaling Data with COM Interop</span></span>
<span data-ttu-id="f4415-103">COM interop는 관리 코드에서 COM 개체를 사용하고 관리되는 개체를 COM에 노출하는 기능을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-103">COM interop provides support for both using COM objects from managed code and exposing managed objects to COM.</span></span> <span data-ttu-id="f4415-104">COM과의 데이터 마샬링 지원은 광범위하며 거의 항상 올바른 마샬링 동작을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-104">Support for marshaling data to and from COM is extensive and almost always provides the correct marshaling behavior.</span></span>  
  
 <span data-ttu-id="f4415-105">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에는 다음과 같은 COM interop 도구가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-105">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] includes the following COM interop tools:</span></span>  
  
- <span data-ttu-id="f4415-106">[형식 라이브러리 가져오기(Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) - COM 형식 라이브러리를 interop 어셈블리로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-106">[Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), which converts a COM type library to an interop assembly.</span></span> <span data-ttu-id="f4415-107">이 어셈블리에서 interop 마샬링 서비스는 관리되는 메모리와 관리되지 않는 메모리 간에 데이터 마샬링을 수행하는 래퍼를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-107">From this assembly, the interop marshaling service generates wrappers that perform data marshaling between managed and unmanaged memory.</span></span>  
  
- <span data-ttu-id="f4415-108">[형식 라이브러리 내보내기(Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) - 어셈블리에서 COM 형식 라이브러리를 생성하고 메서드 호출 중 마샬링을 수행하는 래퍼를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-108">[Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which produces a COM type library from an assembly and generates a wrapper that performs marshaling during method calls.</span></span>  
  
 <span data-ttu-id="f4415-109">다음 섹셕은 마샬러에 추가 형식 정보를 제공할 수 있는(제공해야 하는) 경우 interop 래퍼를 사용자 지정하는 프로세스를 설명하는 항목으로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-109">The following sections link to topics that describe the processes for customizing interop wrappers when you can (or must) supply the marshaler with additional type information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f4415-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f4415-110">In This Section</span></span>  
<span data-ttu-id="f4415-111">[방법: 수동으로 래퍼 만들기](how-to-create-wrappers-manually.md) </span><span class="sxs-lookup"><span data-stu-id="f4415-111">[How to: Create Wrappers Manually](how-to-create-wrappers-manually.md) </span></span>  
<span data-ttu-id="f4415-112">관리 소스 코드에서 COM 래퍼를 수동으로 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-112">Describes how to create a COM wrapper manually in managed source code.</span></span> 
 
 [<span data-ttu-id="f4415-113">방법: 관리 코드 DCOM을 WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f4415-113">How to: Migrate Managed-Code DCOM to WCF</span></span>](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 <span data-ttu-id="f4415-114">보다 안전한 솔루션을 위해 관리되는 DCOM 코드를 WCF로 마이그레이션하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-114">Describes how to migrate managed DCOM code to WCF for the most secure solution.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f4415-115">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f4415-115">Related Sections</span></span>  
 <span data-ttu-id="f4415-116">[COM 데이터 형식](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f4415-116">[COM Data Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span></span>  
 <span data-ttu-id="f4415-117">해당 관리되는 데이터 형식과 관리되지 않는 데이터 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-117">Provides corresponding managed and unmanaged data types.</span></span>  
  
 <span data-ttu-id="f4415-118">[COM 호출 가능 래퍼 사용자 지정](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f4415-118">[Customizing COM Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span></span>  
 <span data-ttu-id="f4415-119">디자인 타임에 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하여 데이터 형식을 명시적으로 마샬링하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-119">Describes how to explicitly marshal data types using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute at design time.</span></span>  
  
 <span data-ttu-id="f4415-120">[런타임 호출 가능 래퍼 사용자 지정](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f4415-120">[Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span></span>  
 <span data-ttu-id="f4415-121">interop 어셈블리에서 형식의 마샬링 동작을 조정하는 방법 및 COM 형식을 수동으로 조정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-121">Describes how to adjust the marshaling behavior of types in an interop assembly and how to define COM types manually.</span></span>  
  
 <span data-ttu-id="f4415-122">[고급 COM 상호 운용성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f4415-122">[Advanced COM Interoperability](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>  
 <span data-ttu-id="f4415-123">COM 구성 요소를 .NET Framework 응용 프로그램으로 통합하는 방법에 대한 추가정보 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-123">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>  
  
 <span data-ttu-id="f4415-124">[어셈블리와 형식 라이브러리 간 변환 요약](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f4415-124">[Assembly to Type Library Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span></span>  
 <span data-ttu-id="f4415-125">어셈블리에서 형식 라이브러리로 내보내기 변환 프로세스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-125">Describes the assembly to type library export conversion process.</span></span>  
  
 <span data-ttu-id="f4415-126">[형식 라이브러리를 어셈블리로 변환 요약](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f4415-126">[Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span></span>  
 <span data-ttu-id="f4415-127">형식 라이브러리에서 어셈블리 가져오기 변환 프로세스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-127">Describes the type library to assembly import conversion process.</span></span>  
  
 <span data-ttu-id="f4415-128">[제네릭 형식을 통한 상호 운용](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f4415-128">[Interoperating Using Generic Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span></span>  
 <span data-ttu-id="f4415-129">COM 상호 운용성을 위해 제네릭 형식을 사용할 때 지원되는 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-129">Describes which actions are supported when using generic types for COM interoperability.</span></span>

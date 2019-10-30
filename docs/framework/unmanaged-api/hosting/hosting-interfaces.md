---
title: 호스팅 인터페이스
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
ms.openlocfilehash: 43b401885bb4de69a06496874f11cec6cdf04b22
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126969"
---
# <a name="hosting-interfaces"></a><span data-ttu-id="46020-102">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46020-102">Hosting Interfaces</span></span>
<span data-ttu-id="46020-103">이 섹션에서는 관리 되지 않는 호스트가 CLR (공용 언어 런타임)을 응용 프로그램에 통합 하는 데 사용할 수 있는 인터페이스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="46020-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="46020-104">.NET Framework 버전 2.0 호스팅 인터페이스는 .NET Framework 버전 1.0 및 1.1 인터페이스를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="46020-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="46020-105">두 인터페이스 집합 간에는 상당한 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46020-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="46020-106">이러한 항목을 혼합 하면 예기치 않은 동작이 발생할 수 있으므로 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46020-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="46020-107">.NET Framework 버전 3.0 및 3.5은 .NET Framework 버전 2.0 호스팅 인터페이스를 사용 하며 호스팅 기능을 도입 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46020-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="46020-108">.NET Framework 4 호스팅 인터페이스는 .NET Framework 2.0 인터페이스를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="46020-108">The .NET Framework 4 hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="46020-109">단원 내용</span><span class="sxs-lookup"><span data-stu-id="46020-109">In This Section</span></span>  
 [<span data-ttu-id="46020-110">사용되지 않는 CLR 호스팅 인터페이스 및 Coclass</span><span class="sxs-lookup"><span data-stu-id="46020-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="46020-111">.NET Framework 버전 1.0 및 1.1에 도입 된 호스팅 인터페이스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="46020-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="46020-112">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46020-112">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="46020-113">.NET Framework 버전 2.0에 도입 된 호스팅 인터페이스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="46020-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="46020-114">.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46020-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="46020-115">.NET Framework 4에서 도입 된 호스팅 인터페이스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="46020-115">Describes the hosting interfaces introduced in the .NET Framework 4.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="46020-116">관련 단원</span><span class="sxs-lookup"><span data-stu-id="46020-116">Related Sections</span></span>  
 [<span data-ttu-id="46020-117">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="46020-117">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="46020-118">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="46020-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="46020-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="46020-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
  
 [<span data-ttu-id="46020-120">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="46020-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
  
 [<span data-ttu-id="46020-121">호스팅</span><span class="sxs-lookup"><span data-stu-id="46020-121">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
  
 <span data-ttu-id="46020-122">[런타임 호스트](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="46020-122">[Runtime Hosts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>

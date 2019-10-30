---
title: 호스팅 구조체
ms.date: 03/30/2017
helpviewer_keywords:
- hosting structures [.NET Framework]
- unmanaged structures [.NET Framework], hosting
- structures [.NET Framework hosting]
ms.assetid: 492e010f-7493-4134-9505-f7008ccdaae6
ms.openlocfilehash: 3d43225574b8794733ee2e83562699276ddc5bab
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126933"
---
# <a name="hosting-structures"></a><span data-ttu-id="a085d-102">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="a085d-102">Hosting Structures</span></span>
<span data-ttu-id="a085d-103">이 섹션에서는 호스팅 API가 사용 하는 관리 되지 않는 구조체에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a085d-103">This section describes the unmanaged structures that the hosting API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a085d-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="a085d-104">In This Section</span></span>  
 [<span data-ttu-id="a085d-105">AssemblyBindInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="a085d-105">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 <span data-ttu-id="a085d-106">참조 된 어셈블리에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a085d-106">Provides detailed information about the referenced assembly.</span></span>  
  
 [<span data-ttu-id="a085d-107">BucketParameters 구조체</span><span class="sxs-lookup"><span data-stu-id="a085d-107">BucketParameters Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md)  
 <span data-ttu-id="a085d-108">이벤트의 형식 이름 및 이벤트와 연결 된 현재 예외에 대 한 매개 변수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a085d-108">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
 [<span data-ttu-id="a085d-109">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="a085d-109">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 <span data-ttu-id="a085d-110">CLR (공용 언어 런타임)의 가비지 수집 메커니즘에 대 한 통계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a085d-110">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
 [<span data-ttu-id="a085d-111">COR_GC_THREAD_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="a085d-111">COR_GC_THREAD_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)  
 <span data-ttu-id="a085d-112">가비지 수집과 관련 된 스레드별 통계를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a085d-112">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
 [<span data-ttu-id="a085d-113">CustomDumpItem 구조체</span><span class="sxs-lookup"><span data-stu-id="a085d-113">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 <span data-ttu-id="a085d-114">오류 보고에서 사용자 지정 덤프에 추가할 항목을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a085d-114">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
 [<span data-ttu-id="a085d-115">MDAInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="a085d-115">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)  
 <span data-ttu-id="a085d-116">MDA (관리 디버깅 도우미) 만들기를 트리거하는 `Event_MDAFired` 이벤트에 대 한 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a085d-116">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
 [<span data-ttu-id="a085d-117">ModuleBindInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="a085d-117">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)  
 <span data-ttu-id="a085d-118">참조 된 모듈 및이 모듈을 포함 하는 어셈블리에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a085d-118">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
 [<span data-ttu-id="a085d-119">StackOverflowInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="a085d-119">StackOverflowInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/stackoverflowinfo-structure.md)  
 <span data-ttu-id="a085d-120">발생 한 오버플로 형식과 오버플로로 인해 throw 된 예외에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a085d-120">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a085d-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="a085d-121">Related Sections</span></span>  
 [<span data-ttu-id="a085d-122">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="a085d-122">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="a085d-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a085d-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
  
 [<span data-ttu-id="a085d-124">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="a085d-124">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="a085d-125">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="a085d-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

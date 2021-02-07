---
description: '자세한 정보: IAssemblyCache 인터페이스'
title: IAssemblyCache 인터페이스
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
ms.openlocfilehash: 29c042fc101180085a697e02376b91b0e1ffd19f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760929"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="e9d08-103">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9d08-103">IAssemblyCache Interface</span></span>

<span data-ttu-id="e9d08-104">Fusion 기술에서 사용할 전역 어셈블리 캐시를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e9d08-104">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9d08-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e9d08-105">Methods</span></span>  
  
|<span data-ttu-id="e9d08-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e9d08-106">Method</span></span>|<span data-ttu-id="e9d08-107">설명</span><span class="sxs-lookup"><span data-stu-id="e9d08-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9d08-108">CreateAssemblyCacheItem 메서드</span><span class="sxs-lookup"><span data-stu-id="e9d08-108">CreateAssemblyCacheItem Method</span></span>](iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="e9d08-109">새 [Iassemblycacheitem](iassemblycacheitem-interface.md)에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e9d08-109">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="e9d08-110">CreateAssemblyScavenger 메서드</span><span class="sxs-lookup"><span data-stu-id="e9d08-110">CreateAssemblyScavenger Method</span></span>](iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="e9d08-111">Fusion 기술에서 내부용으로 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9d08-111">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="e9d08-112">InstallAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="e9d08-112">InstallAssembly Method</span></span>](iassemblycache-installassembly-method.md)|<span data-ttu-id="e9d08-113">지정 된 어셈블리를 전역 어셈블리 캐시에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d08-113">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="e9d08-114">QueryAssemblyInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="e9d08-114">QueryAssemblyInfo Method</span></span>](iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="e9d08-115">지정 된 어셈블리에 대 한 요청 된 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e9d08-115">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="e9d08-116">UninstallAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="e9d08-116">UninstallAssembly Method</span></span>](iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="e9d08-117">전역 어셈블리 캐시에서 지정 된 어셈블리를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d08-117">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9d08-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9d08-118">Requirements</span></span>  

 <span data-ttu-id="e9d08-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e9d08-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9d08-120">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e9d08-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e9d08-121">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9d08-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d08-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9d08-122">See also</span></span>

- [<span data-ttu-id="e9d08-123">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9d08-123">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="e9d08-124">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="e9d08-124">Global Assembly Cache</span></span>](../../app-domains/gac.md)

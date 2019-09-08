---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6dab5fe941fce3c23ba718906b29c80c6d257c2f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796775"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="030c9-102">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="030c9-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="030c9-103">Fusion 기술에서 사용할 전역 어셈블리 캐시를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="030c9-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="030c9-104">메서드</span><span class="sxs-lookup"><span data-stu-id="030c9-104">Methods</span></span>  
  
|<span data-ttu-id="030c9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="030c9-105">Method</span></span>|<span data-ttu-id="030c9-106">Description</span><span class="sxs-lookup"><span data-stu-id="030c9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="030c9-107">CreateAssemblyCacheItem 메서드</span><span class="sxs-lookup"><span data-stu-id="030c9-107">CreateAssemblyCacheItem Method</span></span>](iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="030c9-108">새 [Iassemblycacheitem](iassemblycacheitem-interface.md)에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="030c9-108">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="030c9-109">CreateAssemblyScavenger 메서드</span><span class="sxs-lookup"><span data-stu-id="030c9-109">CreateAssemblyScavenger Method</span></span>](iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="030c9-110">Fusion 기술에서 내부용으로 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="030c9-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="030c9-111">InstallAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="030c9-111">InstallAssembly Method</span></span>](iassemblycache-installassembly-method.md)|<span data-ttu-id="030c9-112">지정 된 어셈블리를 전역 어셈블리 캐시에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="030c9-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="030c9-113">QueryAssemblyInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="030c9-113">QueryAssemblyInfo Method</span></span>](iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="030c9-114">지정 된 어셈블리에 대 한 요청 된 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="030c9-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="030c9-115">UninstallAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="030c9-115">UninstallAssembly Method</span></span>](iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="030c9-116">전역 어셈블리 캐시에서 지정 된 어셈블리를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="030c9-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="030c9-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="030c9-117">Requirements</span></span>  
 <span data-ttu-id="030c9-118">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="030c9-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="030c9-119">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="030c9-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="030c9-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="030c9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="030c9-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="030c9-121">See also</span></span>

- [<span data-ttu-id="030c9-122">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="030c9-122">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="030c9-123">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="030c9-123">Global Assembly Cache</span></span>](../../app-domains/gac.md)

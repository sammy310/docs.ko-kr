---
title: IAssemblyCacheItem 인터페이스
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fba17a2ffad9220acdbc79726efe0d3d4184978a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188554"
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="5a150-102">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a150-102">IAssemblyCacheItem Interface</span></span>
<span data-ttu-id="5a150-103">전역 어셈블리 캐시에서 단일 어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5a150-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a150-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5a150-104">Methods</span></span>  
  
|<span data-ttu-id="5a150-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5a150-105">Method</span></span>|<span data-ttu-id="5a150-106">설명</span><span class="sxs-lookup"><span data-stu-id="5a150-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a150-107">AbortItem 메서드</span><span class="sxs-lookup"><span data-stu-id="5a150-107">AbortItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="5a150-108">전역 어셈블리 캐시에 어셈블리를 해제 되기 전에 정리 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a150-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="5a150-109">Commit 메서드</span><span class="sxs-lookup"><span data-stu-id="5a150-109">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-commit-method.md)|<span data-ttu-id="5a150-110">메모리에 캐시 된 어셈블리 참조를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="5a150-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="5a150-111">CreateStream 메서드</span><span class="sxs-lookup"><span data-stu-id="5a150-111">CreateStream Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-createstream-method.md)|<span data-ttu-id="5a150-112">지정한 이름 및 형식을 사용 하 여 스트림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5a150-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a150-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a150-113">Requirements</span></span>  
 <span data-ttu-id="5a150-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a150-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a150-115">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="5a150-115">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="5a150-116">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="5a150-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5a150-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="5a150-117">See also</span></span>

- [<span data-ttu-id="5a150-118">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a150-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="5a150-119">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="5a150-119">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
- [<span data-ttu-id="5a150-120">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a150-120">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)

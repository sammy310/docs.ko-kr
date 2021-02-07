---
description: '다음에 대 한 자세한 정보: IAssemblyCacheItem 인터페이스'
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
ms.openlocfilehash: 2dcb721f6b65ecca93262f9af2ba355d94bb774d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760869"
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="f3981-103">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3981-103">IAssemblyCacheItem Interface</span></span>

<span data-ttu-id="f3981-104">전역 어셈블리 캐시의 단일 어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f3981-104">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3981-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f3981-105">Methods</span></span>  
  
|<span data-ttu-id="f3981-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f3981-106">Method</span></span>|<span data-ttu-id="f3981-107">설명</span><span class="sxs-lookup"><span data-stu-id="f3981-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3981-108">AbortItem 메서드</span><span class="sxs-lookup"><span data-stu-id="f3981-108">AbortItem Method</span></span>](iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="f3981-109">전역 어셈블리 캐시의 어셈블리가 해제 되기 전에 정리 작업을 수행할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3981-109">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="f3981-110">Commit 메서드</span><span class="sxs-lookup"><span data-stu-id="f3981-110">Commit Method</span></span>](iassemblycacheitem-commit-method.md)|<span data-ttu-id="f3981-111">캐시 된 어셈블리 참조를 메모리에 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="f3981-111">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="f3981-112">CreateStream 메서드</span><span class="sxs-lookup"><span data-stu-id="f3981-112">CreateStream Method</span></span>](iassemblycacheitem-createstream-method.md)|<span data-ttu-id="f3981-113">지정 된 이름 및 형식을 사용 하 여 스트림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3981-113">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3981-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f3981-114">Requirements</span></span>  

 <span data-ttu-id="f3981-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3981-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3981-116">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="f3981-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f3981-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3981-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3981-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3981-118">See also</span></span>

- [<span data-ttu-id="f3981-119">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3981-119">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="f3981-120">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="f3981-120">Global Assembly Cache</span></span>](../../app-domains/gac.md)
- [<span data-ttu-id="f3981-121">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3981-121">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)

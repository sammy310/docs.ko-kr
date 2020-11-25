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
ms.openlocfilehash: 72922d1fd0f8ae5e59fe76c7aa50f9c52dcd5302
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719946"
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="a1780-102">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1780-102">IAssemblyCacheItem Interface</span></span>

<span data-ttu-id="a1780-103">전역 어셈블리 캐시의 단일 어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a1780-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a1780-104">메서드</span><span class="sxs-lookup"><span data-stu-id="a1780-104">Methods</span></span>  
  
|<span data-ttu-id="a1780-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a1780-105">Method</span></span>|<span data-ttu-id="a1780-106">설명</span><span class="sxs-lookup"><span data-stu-id="a1780-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1780-107">AbortItem 메서드</span><span class="sxs-lookup"><span data-stu-id="a1780-107">AbortItem Method</span></span>](iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="a1780-108">전역 어셈블리 캐시의 어셈블리가 해제 되기 전에 정리 작업을 수행할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1780-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="a1780-109">Commit 메서드</span><span class="sxs-lookup"><span data-stu-id="a1780-109">Commit Method</span></span>](iassemblycacheitem-commit-method.md)|<span data-ttu-id="a1780-110">캐시 된 어셈블리 참조를 메모리에 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="a1780-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="a1780-111">CreateStream 메서드</span><span class="sxs-lookup"><span data-stu-id="a1780-111">CreateStream Method</span></span>](iassemblycacheitem-createstream-method.md)|<span data-ttu-id="a1780-112">지정 된 이름 및 형식을 사용 하 여 스트림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a1780-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1780-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1780-113">Requirements</span></span>  

 <span data-ttu-id="a1780-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1780-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1780-115">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="a1780-115">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a1780-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1780-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1780-117">참조</span><span class="sxs-lookup"><span data-stu-id="a1780-117">See also</span></span>

- [<span data-ttu-id="a1780-118">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1780-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="a1780-119">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="a1780-119">Global Assembly Cache</span></span>](../../app-domains/gac.md)
- [<span data-ttu-id="a1780-120">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1780-120">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)

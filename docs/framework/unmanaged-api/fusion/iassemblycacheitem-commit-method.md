---
title: IAssemblyCacheItem::Commit 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.Commit
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::Commit
helpviewer_keywords:
- IAssemblyCacheItem::Commit method [.NET Framework fusion]
- Commit method, IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: c2321f17-f46f-4815-ae41-b28678753613
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d234910429961a8a0add1d88d0c0eed96ed12a58
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496211"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="2c0ce-102">IAssemblyCacheItem::Commit 메서드</span><span class="sxs-lookup"><span data-stu-id="2c0ce-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="2c0ce-103">메모리에 캐시 된 어셈블리 참조를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0ce-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c0ce-104">구문</span><span class="sxs-lookup"><span data-stu-id="2c0ce-104">Syntax</span></span>  
  
```  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c0ce-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c0ce-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="2c0ce-106">[in] 같은 값이 지원에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="2c0ce-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="2c0ce-107">[out, optional] 작업의 결과 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2c0ce-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c0ce-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c0ce-108">Requirements</span></span>  
 <span data-ttu-id="2c0ce-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2c0ce-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c0ce-110">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="2c0ce-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2c0ce-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c0ce-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c0ce-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="2c0ce-112">See also</span></span>
- [<span data-ttu-id="2c0ce-113">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c0ce-113">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)

---
description: '다음에 대 한 자세한 정보: IAssemblyCacheItem:: Commit 메서드'
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
ms.openlocfilehash: bd73bb9099090089e52d52009cfef309b33adc53
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760858"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="15ea1-103">IAssemblyCacheItem::Commit 메서드</span><span class="sxs-lookup"><span data-stu-id="15ea1-103">IAssemblyCacheItem::Commit Method</span></span>

<span data-ttu-id="15ea1-104">캐시 된 어셈블리 참조를 메모리에 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="15ea1-104">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15ea1-105">구문</span><span class="sxs-lookup"><span data-stu-id="15ea1-105">Syntax</span></span>  
  
```cpp  
HRESULT Commit (  
    [in] DWORD dwFlags,
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15ea1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="15ea1-106">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="15ea1-107">진행 Fusion에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="15ea1-107">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="15ea1-108">[out, 선택 사항] 작업의 결과를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="15ea1-108">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15ea1-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15ea1-109">Requirements</span></span>  

 <span data-ttu-id="15ea1-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="15ea1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15ea1-111">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="15ea1-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="15ea1-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15ea1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ea1-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15ea1-113">See also</span></span>

- [<span data-ttu-id="15ea1-114">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ea1-114">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)

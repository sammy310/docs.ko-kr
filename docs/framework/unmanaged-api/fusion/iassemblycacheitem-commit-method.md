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
ms.openlocfilehash: f840438e175790a2b4c97302963b910f98dffb7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176567"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="ec2a7-102">IAssemblyCacheItem::Commit 메서드</span><span class="sxs-lookup"><span data-stu-id="ec2a7-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="ec2a7-103">캐시된 어셈블리 참조를 메모리에 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2a7-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec2a7-104">구문</span><span class="sxs-lookup"><span data-stu-id="ec2a7-104">Syntax</span></span>  
  
```cpp  
HRESULT Commit (  
    [in] DWORD dwFlags,
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec2a7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ec2a7-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="ec2a7-106">【인】 Fusion.idl에 정의된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="ec2a7-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="ec2a7-107">[아웃, 선택 사항] 작업 결과를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ec2a7-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec2a7-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ec2a7-108">Requirements</span></span>  
 <span data-ttu-id="ec2a7-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ec2a7-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec2a7-110">**헤더:** 퓨전.h</span><span class="sxs-lookup"><span data-stu-id="ec2a7-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ec2a7-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec2a7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec2a7-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec2a7-112">See also</span></span>

- [<span data-ttu-id="ec2a7-113">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec2a7-113">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)

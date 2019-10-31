---
title: ICorPublishAppDomainEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type:
- apiref
ms.openlocfilehash: 0553d8b07e3a16dc31474b5470ba2dd8ba365cb2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140508"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="88faf-102">ICorPublishAppDomainEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="88faf-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="88faf-103">현재 위치에서 시작 하 여 현재 프로세스에 있는 지정 된 수의 응용 프로그램 도메인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="88faf-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88faf-104">구문</span><span class="sxs-lookup"><span data-stu-id="88faf-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88faf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="88faf-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="88faf-106">진행 검색할 요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="88faf-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="88faf-107">제한이 각각 응용 프로그램 도메인을 나타내는, 검색 된 [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) 개체의 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="88faf-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="88faf-108">제한이 실제로 반환 된 응용 프로그램 도메인의 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="88faf-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="88faf-109">`celt` 일 경우이 값은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88faf-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88faf-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="88faf-110">Requirements</span></span>  
 <span data-ttu-id="88faf-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88faf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88faf-112">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="88faf-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="88faf-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88faf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88faf-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88faf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88faf-115">참조</span><span class="sxs-lookup"><span data-stu-id="88faf-115">See also</span></span>

- [<span data-ttu-id="88faf-116">ICorPublishAppDomainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88faf-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)

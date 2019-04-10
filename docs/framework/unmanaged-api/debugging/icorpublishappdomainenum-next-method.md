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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c14d364320c82f061ef606a402563dacfce28139
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186240"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="b84dc-102">ICorPublishAppDomainEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="b84dc-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="b84dc-103">현재 위치에서 시작 하 여 프로세스에 현재 존재 하는 응용 프로그램 도메인의 지정 된 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b84dc-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b84dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="b84dc-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b84dc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b84dc-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b84dc-106">[in] 검색할 요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b84dc-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="b84dc-107">[out] 검색의 배열에 대 한 포인터 [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) 각각 응용 프로그램 도메인을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b84dc-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b84dc-108">[out] 실제로 반환 된 응용 프로그램 도메인 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b84dc-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="b84dc-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="b84dc-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b84dc-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b84dc-110">Requirements</span></span>  
 <span data-ttu-id="b84dc-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b84dc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b84dc-112">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="b84dc-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b84dc-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b84dc-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b84dc-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="b84dc-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b84dc-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="b84dc-115">See also</span></span>

- [<span data-ttu-id="b84dc-116">ICorPublishAppDomainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b84dc-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)

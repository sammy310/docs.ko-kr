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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986650"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="3625a-102">ICorPublishAppDomainEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="3625a-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="3625a-103">현재 위치에서 시작 하 여 프로세스에 현재 존재 하는 응용 프로그램 도메인의 지정 된 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3625a-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3625a-104">구문</span><span class="sxs-lookup"><span data-stu-id="3625a-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3625a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3625a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="3625a-106">[in] 검색할 요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3625a-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="3625a-107">[out] 검색의 배열에 대 한 포인터 [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) 각각 응용 프로그램 도메인을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3625a-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="3625a-108">[out] 실제로 반환 된 응용 프로그램 도메인 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3625a-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="3625a-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="3625a-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3625a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3625a-110">Requirements</span></span>  
 <span data-ttu-id="3625a-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3625a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3625a-112">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="3625a-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3625a-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3625a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3625a-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3625a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3625a-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="3625a-115">See also</span></span>

- [<span data-ttu-id="3625a-116">ICorPublishAppDomainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3625a-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)

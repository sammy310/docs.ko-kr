---
description: '자세히 알아보기: ICorPublishAppDomainEnum:: Next 메서드'
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
ms.openlocfilehash: 8e8255aa2326c6f0678132f5735d6cdf504dcbd0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721725"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="b2115-103">ICorPublishAppDomainEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="b2115-103">ICorPublishAppDomainEnum::Next Method</span></span>

<span data-ttu-id="b2115-104">현재 위치에서 시작 하 여 현재 프로세스에 있는 지정 된 수의 응용 프로그램 도메인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b2115-104">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2115-105">구문</span><span class="sxs-lookup"><span data-stu-id="b2115-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2115-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2115-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="b2115-107">진행 검색할 요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b2115-107">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="b2115-108">제한이 각각 응용 프로그램 도메인을 나타내는, 검색 된 [ICorPublishAppDomain](icorpublishappdomain-interface.md) 개체의 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b2115-108">[out] A pointer to the array of retrieved [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b2115-109">제한이 실제로 반환 된 응용 프로그램 도메인의 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b2115-109">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="b2115-110">이 일 경우이 값은 null 일 수 있습니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="b2115-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2115-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2115-111">Requirements</span></span>  

 <span data-ttu-id="b2115-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2115-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2115-113">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="b2115-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b2115-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2115-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2115-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2115-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2115-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2115-116">See also</span></span>

- [<span data-ttu-id="b2115-117">ICorPublishAppDomainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b2115-117">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)

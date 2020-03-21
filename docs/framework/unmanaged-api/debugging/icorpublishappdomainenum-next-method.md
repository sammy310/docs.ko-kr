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
ms.openlocfilehash: 6f7f400c51ded0b98c0c2286cb6f90bbd77e47d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178394"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="ea929-102">ICorPublishAppDomainEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="ea929-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="ea929-103">현재 위치에서 시작하여 프로세스에 현재 존재하는 지정된 수의 응용 프로그램 도메인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ea929-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea929-104">구문</span><span class="sxs-lookup"><span data-stu-id="ea929-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea929-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ea929-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ea929-106">【인】 검색할 요소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ea929-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="ea929-107">【아웃】 검색된 [ICorPublishAppDomain](icorpublishappdomain-interface.md) 개체의 배열에 대한 포인터로, 각 개체는 응용 프로그램 도메인을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ea929-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ea929-108">【아웃】 실제로 반환된 응용 프로그램 도메인 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ea929-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="ea929-109">이 `celt` 값은 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea929-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea929-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ea929-110">Requirements</span></span>  
 <span data-ttu-id="ea929-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea929-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea929-112">**헤더:** 코르펍.idl, 코르펍.h</span><span class="sxs-lookup"><span data-stu-id="ea929-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ea929-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea929-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea929-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea929-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea929-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea929-115">See also</span></span>

- [<span data-ttu-id="ea929-116">ICorPublishAppDomainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea929-116">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)

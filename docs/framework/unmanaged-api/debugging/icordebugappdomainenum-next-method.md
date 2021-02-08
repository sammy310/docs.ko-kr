---
description: '자세히 알아보기: ICorDebugAppDomainEnum:: Next 메서드'
title: ICorDebugAppDomainEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type:
- apiref
ms.openlocfilehash: ac5397250e661b4ed380b3272744957f86e1a07b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791532"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="024d9-103">ICorDebugAppDomainEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="024d9-103">ICorDebugAppDomainEnum::Next Method</span></span>

<span data-ttu-id="024d9-104">현재 커서 위치에서 시작 하 여 컬렉션에서 지정 된 수의 응용 프로그램 도메인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="024d9-104">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="024d9-105">구문</span><span class="sxs-lookup"><span data-stu-id="024d9-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="024d9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="024d9-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="024d9-107">진행 검색할 응용 프로그램 도메인의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="024d9-107">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="024d9-108">제한이 각각 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="024d9-108">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="024d9-109">제한이 실제로 반환 된 응용 프로그램 도메인의 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="024d9-109">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="024d9-110">이 일 경우이 값은 null 일 수 있습니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="024d9-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="024d9-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="024d9-111">Requirements</span></span>  

 <span data-ttu-id="024d9-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="024d9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="024d9-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="024d9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="024d9-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="024d9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="024d9-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="024d9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

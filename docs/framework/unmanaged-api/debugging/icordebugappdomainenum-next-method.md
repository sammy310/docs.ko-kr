---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fefc933cc84fede1f3dea16d4b13e09801a96e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996153"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="09d7e-102">ICorDebugAppDomainEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="09d7e-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="09d7e-103">현재 커서 위치부터 컬렉션에서 지정 된 응용 프로그램 도메인 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="09d7e-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09d7e-104">구문</span><span class="sxs-lookup"><span data-stu-id="09d7e-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09d7e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09d7e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="09d7e-106">[in] 검색할 응용 프로그램 도메인의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="09d7e-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="09d7e-107">[out] 포인터의 배열에는 각 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="09d7e-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="09d7e-108">[out] 실제로 반환 된 응용 프로그램 도메인 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="09d7e-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="09d7e-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="09d7e-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09d7e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09d7e-110">Requirements</span></span>  
 <span data-ttu-id="09d7e-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="09d7e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09d7e-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09d7e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09d7e-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09d7e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09d7e-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09d7e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

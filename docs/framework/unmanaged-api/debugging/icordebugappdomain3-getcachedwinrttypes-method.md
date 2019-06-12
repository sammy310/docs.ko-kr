---
title: ICorDebugAppDomain3::GetCachedWinRTTypes 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7e2685d17f3dd32db295f926fc19121d29e1752
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025918"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="1fb72-102">ICorDebugAppDomain3::GetCachedWinRTTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="1fb72-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="1fb72-103">캐시 된 모든 Windows 런타임 형식에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1fb72-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fb72-104">구문</span><span class="sxs-lookup"><span data-stu-id="1fb72-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fb72-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1fb72-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="1fb72-106">[out] 에 대 한 포인터를 [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) 응용 프로그램 도메인에서 현재 관리 되는 Windows 런타임 형식 표현을 열거할 수 있는 인터페이스 개체를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fb72-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fb72-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1fb72-107">Requirements</span></span>  
 <span data-ttu-id="1fb72-108">**플랫폼:** Windows 런타임</span><span class="sxs-lookup"><span data-stu-id="1fb72-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="1fb72-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fb72-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fb72-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fb72-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fb72-111">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fb72-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fb72-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="1fb72-112">See also</span></span>

- [<span data-ttu-id="1fb72-113">ICorDebugAppDomain3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1fb72-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)

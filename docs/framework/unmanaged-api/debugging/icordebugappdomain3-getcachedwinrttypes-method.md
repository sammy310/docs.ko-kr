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
ms.openlocfilehash: 4ba981d86f90af449820ce13aa847169ca877429
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737766"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="97593-102">ICorDebugAppDomain3::GetCachedWinRTTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="97593-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="97593-103">캐시 된 모든 Windows 런타임 형식에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="97593-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97593-104">구문</span><span class="sxs-lookup"><span data-stu-id="97593-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="97593-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="97593-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="97593-106">[out] 에 대 한 포인터를 [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) 응용 프로그램 도메인에서 현재 관리 되는 Windows 런타임 형식 표현을 열거할 수 있는 인터페이스 개체를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="97593-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97593-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97593-107">Requirements</span></span>  
 <span data-ttu-id="97593-108">**플랫폼:** Windows 런타임</span><span class="sxs-lookup"><span data-stu-id="97593-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="97593-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97593-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97593-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97593-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97593-111">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97593-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97593-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="97593-112">See also</span></span>

- [<span data-ttu-id="97593-113">ICorDebugAppDomain3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97593-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)

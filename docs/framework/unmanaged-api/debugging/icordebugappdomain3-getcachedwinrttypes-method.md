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
ms.openlocfilehash: 5e0df443e691292817ff37900fbc87204a8325ab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684501"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="3985d-102">ICorDebugAppDomain3::GetCachedWinRTTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="3985d-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>

<span data-ttu-id="3985d-103">모든 캐시 된 Windows 런타임 형식에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3985d-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3985d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3985d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3985d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3985d-105">Parameters</span></span>  

 `ppGuidToTypeEnum`  
 <span data-ttu-id="3985d-106">제한이 응용 프로그램 도메인에 현재 로드 된 Windows 런타임 형식의 관리 되는 표현을 열거할 수 있는 [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md) interface 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3985d-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3985d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3985d-107">Requirements</span></span>  

 <span data-ttu-id="3985d-108">**플랫폼:** Windows 런타임</span><span class="sxs-lookup"><span data-stu-id="3985d-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="3985d-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3985d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3985d-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3985d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3985d-111">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3985d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3985d-112">참조</span><span class="sxs-lookup"><span data-stu-id="3985d-112">See also</span></span>

- [<span data-ttu-id="3985d-113">ICorDebugAppDomain3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3985d-113">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)

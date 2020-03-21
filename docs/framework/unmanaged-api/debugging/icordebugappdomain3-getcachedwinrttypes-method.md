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
ms.openlocfilehash: e5fd1730bbe5b6f2905691dce41a7f503227534a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179080"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="64030-102">ICorDebugAppDomain3::GetCachedWinRTTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="64030-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="64030-103">캐시된 모든 Windows 런타임 유형에 대한 열거형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="64030-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64030-104">구문</span><span class="sxs-lookup"><span data-stu-id="64030-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="64030-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="64030-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="64030-106">【아웃】 응용 프로그램 도메인에 현재 로드된 Windows 런타임 형식의 관리되는 표현을 열거할 수 있는 [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md) 인터페이스 개체에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="64030-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64030-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="64030-107">Requirements</span></span>  
 <span data-ttu-id="64030-108">**플랫폼:** 윈도우 런타임</span><span class="sxs-lookup"><span data-stu-id="64030-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="64030-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64030-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64030-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64030-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64030-111">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64030-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64030-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64030-112">See also</span></span>

- [<span data-ttu-id="64030-113">ICorDebugAppDomain3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64030-113">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)

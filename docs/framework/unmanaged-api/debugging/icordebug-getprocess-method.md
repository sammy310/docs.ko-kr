---
title: ICorDebug::GetProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::GetProcess method [.NET Framework debugging]
ms.assetid: 10a40ba0-1b65-4721-bd11-cf12d57b280d
topic_type:
- apiref
ms.openlocfilehash: 46c2b444984c5a0062f1cfbc0cd29dbe409b16fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723443"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="94b6f-102">ICorDebug::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="94b6f-102">ICorDebug::GetProcess Method</span></span>

<span data-ttu-id="94b6f-103">지정 된 프로세스에 대 한 "ICorDebugProcess" 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="94b6f-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94b6f-104">구문</span><span class="sxs-lookup"><span data-stu-id="94b6f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94b6f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="94b6f-105">Parameters</span></span>  

 `dwProcessId`  
 <span data-ttu-id="94b6f-106">진행 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="94b6f-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="94b6f-107">제한이 지정 된 프로세스의 인스턴스 주소에 `ICorDebugProcess` 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="94b6f-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94b6f-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94b6f-108">Requirements</span></span>  

 <span data-ttu-id="94b6f-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94b6f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94b6f-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94b6f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94b6f-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94b6f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94b6f-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94b6f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94b6f-113">참조</span><span class="sxs-lookup"><span data-stu-id="94b6f-113">See also</span></span>

- [<span data-ttu-id="94b6f-114">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94b6f-114">ICorDebug Interface</span></span>](icordebug-interface.md)

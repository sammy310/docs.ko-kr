---
title: ICorDebug::EnumerateProcesses 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.EnumerateProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- EnumerateProcesses
helpviewer_keywords:
- EnumerateProcesses method [.NET Framework debugging]
- ICorDebug::EnumerateProcesses method [.NET Framework debugging]
ms.assetid: ba25d166-1d28-4f1d-aca2-de298bbca669
topic_type:
- apiref
ms.openlocfilehash: bf672c90cdbb9e9fb66105820a264a49601b38d7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723456"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="3d9d5-102">ICorDebug::EnumerateProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="3d9d5-102">ICorDebug::EnumerateProcesses Method</span></span>

<span data-ttu-id="3d9d5-103">디버깅 중인 프로세스에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d9d5-104">구문</span><span class="sxs-lookup"><span data-stu-id="3d9d5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d9d5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3d9d5-105">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="3d9d5-106">디버그할 프로세스의 열거자 인 ICorDebugProcessEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d9d5-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d9d5-107">Requirements</span></span>  

 <span data-ttu-id="3d9d5-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d9d5-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d9d5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d9d5-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d9d5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d9d5-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d9d5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d9d5-112">참조</span><span class="sxs-lookup"><span data-stu-id="3d9d5-112">See also</span></span>

- [<span data-ttu-id="3d9d5-113">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d9d5-113">ICorDebug Interface</span></span>](icordebug-interface.md)

---
description: '자세히 알아보기: ICorDebug:: EnumerateProcesses 메서드'
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
ms.openlocfilehash: 44ee21a820a1c9f94f1d66c93ff040b504bfcc93
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791584"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="d532d-103">ICorDebug::EnumerateProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="d532d-103">ICorDebug::EnumerateProcesses Method</span></span>

<span data-ttu-id="d532d-104">디버깅 중인 프로세스에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d532d-104">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d532d-105">구문</span><span class="sxs-lookup"><span data-stu-id="d532d-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d532d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d532d-106">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="d532d-107">디버그할 프로세스의 열거자 인 ICorDebugProcessEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d532d-107">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d532d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d532d-108">Requirements</span></span>  

 <span data-ttu-id="d532d-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d532d-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d532d-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d532d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d532d-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d532d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d532d-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d532d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d532d-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d532d-113">See also</span></span>

- [<span data-ttu-id="d532d-114">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d532d-114">ICorDebug Interface</span></span>](icordebug-interface.md)

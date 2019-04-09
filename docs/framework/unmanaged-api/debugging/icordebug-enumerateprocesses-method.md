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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7bc82c506cf7e223e672a62ca74b215cac870e50
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123844"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="3f9fc-102">ICorDebug::EnumerateProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="3f9fc-102">ICorDebug::EnumerateProcesses Method</span></span>
<span data-ttu-id="3f9fc-103">디버그 중인 프로세스에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f9fc-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f9fc-104">구문</span><span class="sxs-lookup"><span data-stu-id="3f9fc-104">Syntax</span></span>  
  
```  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f9fc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f9fc-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="3f9fc-106">디버깅 중인 프로세스에 대 한 열거자는 ICorDebugProcessEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9fc-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f9fc-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f9fc-107">Requirements</span></span>  
 <span data-ttu-id="3f9fc-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f9fc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f9fc-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f9fc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f9fc-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f9fc-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3f9fc-111">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="3f9fc-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3f9fc-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="3f9fc-112">See also</span></span>

- [<span data-ttu-id="3f9fc-113">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f9fc-113">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

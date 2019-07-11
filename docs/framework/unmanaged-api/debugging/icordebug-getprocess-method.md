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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e77046745381d3ecc35c24d5af3f9181b9132e9e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738154"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="60d59-102">ICorDebug::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="60d59-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="60d59-103">지정된 된 프로세스에 대 한 "ICorDebugProcess" 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="60d59-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60d59-104">구문</span><span class="sxs-lookup"><span data-stu-id="60d59-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60d59-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="60d59-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="60d59-106">[in] 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="60d59-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="60d59-107">[out] 주소에 대 한 포인터를 `ICorDebugProcess` 지정된 된 프로세스에 대 한 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="60d59-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60d59-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60d59-108">Requirements</span></span>  
 <span data-ttu-id="60d59-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="60d59-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60d59-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60d59-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60d59-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60d59-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60d59-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60d59-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60d59-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="60d59-113">See also</span></span>

- [<span data-ttu-id="60d59-114">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60d59-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

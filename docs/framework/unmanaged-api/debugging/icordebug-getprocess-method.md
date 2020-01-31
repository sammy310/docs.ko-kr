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
ms.openlocfilehash: 2762d0680c5299732196cafe09f6e346e873f19a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785146"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="9416e-102">ICorDebug::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="9416e-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="9416e-103">지정 된 프로세스에 대 한 "ICorDebugProcess" 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9416e-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9416e-104">구문</span><span class="sxs-lookup"><span data-stu-id="9416e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9416e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9416e-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="9416e-106">진행 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9416e-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="9416e-107">제한이 지정 된 프로세스에 대 한 `ICorDebugProcess` 인스턴스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9416e-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9416e-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9416e-108">Requirements</span></span>  
 <span data-ttu-id="9416e-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9416e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9416e-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9416e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9416e-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9416e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9416e-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9416e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9416e-113">참조</span><span class="sxs-lookup"><span data-stu-id="9416e-113">See also</span></span>

- [<span data-ttu-id="9416e-114">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9416e-114">ICorDebug Interface</span></span>](icordebug-interface.md)

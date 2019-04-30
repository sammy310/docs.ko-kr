---
title: ICorDebugModule2::GetJITCompilerFlags 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.GetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::GetJITCompilerFlags
helpviewer_keywords:
- GetJITCompilerFlags method [.NET Framework debugging]
- ICorDebugModule2::GetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: 7212d9f4-989b-44e3-b8d4-ffc35922f6a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77f4e745e4bd45be51b497fdd5bab95cd24c9685
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994814"
---
# <a name="icordebugmodule2getjitcompilerflags-method"></a><span data-ttu-id="5626f-102">ICorDebugModule2::GetJITCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="5626f-102">ICorDebugModule2::GetJITCompilerFlags Method</span></span>
<span data-ttu-id="5626f-103">이 ICorDebugModule2 컴파일하는 시간 (JIT)를 제어 하는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5626f-103">Gets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5626f-104">구문</span><span class="sxs-lookup"><span data-stu-id="5626f-104">Syntax</span></span>  
  
```  
HRESULT GetJITCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5626f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5626f-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="5626f-106">[out] 값에 대 한 포인터를 [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) JIT 컴파일을 제어 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5626f-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that controls the JIT compilation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5626f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5626f-107">Requirements</span></span>  
 <span data-ttu-id="5626f-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5626f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5626f-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5626f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5626f-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5626f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5626f-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5626f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

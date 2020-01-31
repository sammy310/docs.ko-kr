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
ms.openlocfilehash: ab6551ba70ed4cd154b166eeb92138b6550d2cb2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792974"
---
# <a name="icordebugmodule2getjitcompilerflags-method"></a><span data-ttu-id="cd085-102">ICorDebugModule2::GetJITCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="cd085-102">ICorDebugModule2::GetJITCompilerFlags Method</span></span>
<span data-ttu-id="cd085-103">이 ICorDebugModule2의 JIT (just-in-time) 컴파일을 제어 하는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd085-103">Gets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd085-104">구문</span><span class="sxs-lookup"><span data-stu-id="cd085-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJITCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd085-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cd085-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="cd085-106">제한이 JIT 컴파일을 제어 하는 [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cd085-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that controls the JIT compilation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd085-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd085-107">Requirements</span></span>  
 <span data-ttu-id="cd085-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd085-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd085-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd085-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd085-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd085-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd085-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd085-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

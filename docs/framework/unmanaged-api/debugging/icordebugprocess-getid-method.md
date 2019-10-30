---
title: ICorDebugProcess::GetID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetID
helpviewer_keywords:
- GetID method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetID method [.NET Framework debugging]
ms.assetid: b0ba8453-fa7e-4c14-93e5-335409cd4a47
topic_type:
- apiref
ms.openlocfilehash: ae0c23e3d48df6add8951a6d90029185a99bb323
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128838"
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="3c112-102">ICorDebugProcess::GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="3c112-102">ICorDebugProcess::GetID Method</span></span>
<span data-ttu-id="3c112-103">프로세스의 OS (운영 체제) ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3c112-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c112-104">구문</span><span class="sxs-lookup"><span data-stu-id="3c112-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c112-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3c112-105">Parameters</span></span>  
 `pdwProcessId`  
 <span data-ttu-id="3c112-106">제한이 프로세스의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3c112-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c112-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c112-107">Requirements</span></span>  
 <span data-ttu-id="3c112-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c112-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c112-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c112-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c112-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c112-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c112-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c112-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

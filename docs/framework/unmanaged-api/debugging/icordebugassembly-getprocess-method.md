---
title: ICorDebugAssembly::GetProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type:
- apiref
ms.openlocfilehash: 49b234b065eb66dc2ec0bc7e991117c5b54a92f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73196344"
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="41855-102">ICorDebugAssembly::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="41855-102">ICorDebugAssembly::GetProcess Method</span></span>
<span data-ttu-id="41855-103">이 ICorDebugAssembly 인스턴스가 실행 되 고 있는 프로세스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="41855-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41855-104">구문</span><span class="sxs-lookup"><span data-stu-id="41855-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41855-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="41855-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="41855-106">제한이 프로세스를 나타내는 ICorDebugProcess 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="41855-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41855-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41855-107">Requirements</span></span>  
 <span data-ttu-id="41855-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41855-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41855-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41855-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41855-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41855-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41855-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41855-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

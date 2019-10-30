---
title: ICorDebugProcess::GetHandle 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type:
- apiref
ms.openlocfilehash: e4061580d59b0cf2a6e6e481d5242005e9452caf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128868"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="74a86-102">ICorDebugProcess::GetHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="74a86-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="74a86-103">프로세스에 대 한 핸들을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="74a86-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74a86-104">구문</span><span class="sxs-lookup"><span data-stu-id="74a86-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74a86-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="74a86-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="74a86-106">제한이 프로세스에 대 한 핸들에 해당 하는 `HPROCESS`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="74a86-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74a86-107">주의</span><span class="sxs-lookup"><span data-stu-id="74a86-107">Remarks</span></span>  
 <span data-ttu-id="74a86-108">검색 된 핸들은 디버깅 인터페이스가 소유 합니다.</span><span class="sxs-lookup"><span data-stu-id="74a86-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="74a86-109">디버거는 사용 하기 전에 핸들을 복제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74a86-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74a86-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="74a86-110">Requirements</span></span>  
 <span data-ttu-id="74a86-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74a86-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74a86-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74a86-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74a86-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74a86-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74a86-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74a86-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

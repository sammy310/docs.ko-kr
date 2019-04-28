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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5d81564a34ed8e7ef75840e3a174661c36f5411
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994498"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="7b85a-102">ICorDebugProcess::GetHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="7b85a-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="7b85a-103">프로세스에 대 한 핸들을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b85a-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b85a-104">구문</span><span class="sxs-lookup"><span data-stu-id="7b85a-104">Syntax</span></span>  
  
```  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b85a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b85a-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="7b85a-106">[out] 에 대 한 포인터는 `HPROCESS` 프로세스에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="7b85a-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b85a-107">설명</span><span class="sxs-lookup"><span data-stu-id="7b85a-107">Remarks</span></span>  
 <span data-ttu-id="7b85a-108">디버깅 인터페이스에 검색된 핸들을 소유 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b85a-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="7b85a-109">디버거 사용 하 여 핸들을 복제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b85a-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b85a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b85a-110">Requirements</span></span>  
 <span data-ttu-id="7b85a-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b85a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b85a-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b85a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b85a-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b85a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b85a-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b85a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

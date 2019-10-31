---
title: ICorDebugProcess::EnumerateAppDomains 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnumerateAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnumerateAppDomains
helpviewer_keywords:
- ICorDebugProcess::EnumerateAppDomains method [.NET Framework debugging]
- EnumerateAppDomains method [.NET Framework debugging]
ms.assetid: d508981f-e2b2-445b-a649-69951c22702d
topic_type:
- apiref
ms.openlocfilehash: e09e25503ad00ab3542f0c4f50221b6014b25561
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128890"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="e07a3-102">ICorDebugProcess::EnumerateAppDomains 메서드</span><span class="sxs-lookup"><span data-stu-id="e07a3-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="e07a3-103">이 프로세스의 모든 응용 프로그램 도메인을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e07a3-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e07a3-104">구문</span><span class="sxs-lookup"><span data-stu-id="e07a3-104">Syntax</span></span>  
  
``` cpp 
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e07a3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e07a3-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="e07a3-106">제한이 이 프로세스의 응용 프로그램 도메인에 대 한 열거자 인 [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) 의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e07a3-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e07a3-107">주의</span><span class="sxs-lookup"><span data-stu-id="e07a3-107">Remarks</span></span>  
 <span data-ttu-id="e07a3-108">이 메서드는 [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) 콜백 전에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e07a3-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e07a3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e07a3-109">Requirements</span></span>  
 <span data-ttu-id="e07a3-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e07a3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e07a3-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e07a3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e07a3-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e07a3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e07a3-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e07a3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

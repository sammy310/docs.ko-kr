---
description: '자세히 알아보기: ICorDebugProcess:: EnumerateAppDomains 메서드'
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
ms.openlocfilehash: d212fafe7ae1355ba69e07b88c3b96119371fe43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691525"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="7d813-103">ICorDebugProcess::EnumerateAppDomains 메서드</span><span class="sxs-lookup"><span data-stu-id="7d813-103">ICorDebugProcess::EnumerateAppDomains Method</span></span>

<span data-ttu-id="7d813-104">이 프로세스의 모든 응용 프로그램 도메인을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d813-104">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d813-105">구문</span><span class="sxs-lookup"><span data-stu-id="7d813-105">Syntax</span></span>  
  
``` cpp
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d813-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d813-106">Parameters</span></span>  

 `ppAppDomains`  
 <span data-ttu-id="7d813-107">제한이 이 프로세스의 응용 프로그램 도메인에 대 한 열거자 인 [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) 의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7d813-107">[out] A pointer to the address of an [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d813-108">설명</span><span class="sxs-lookup"><span data-stu-id="7d813-108">Remarks</span></span>  

 <span data-ttu-id="7d813-109">이 메서드는 [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) 콜백 전에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d813-109">This method can be used before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d813-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d813-110">Requirements</span></span>  

 <span data-ttu-id="7d813-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d813-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d813-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d813-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d813-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d813-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d813-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d813-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

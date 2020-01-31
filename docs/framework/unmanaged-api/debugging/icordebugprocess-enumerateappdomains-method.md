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
ms.openlocfilehash: 35e3e37b1487b5dda9945402c6a3338384147f9a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792636"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="ca9b4-102">ICorDebugProcess::EnumerateAppDomains 메서드</span><span class="sxs-lookup"><span data-stu-id="ca9b4-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="ca9b4-103">이 프로세스의 모든 응용 프로그램 도메인을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca9b4-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca9b4-104">구문</span><span class="sxs-lookup"><span data-stu-id="ca9b4-104">Syntax</span></span>  
  
``` cpp 
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca9b4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ca9b4-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="ca9b4-106">제한이 이 프로세스의 응용 프로그램 도메인에 대 한 열거자 인 [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) 의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ca9b4-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca9b4-107">주의</span><span class="sxs-lookup"><span data-stu-id="ca9b4-107">Remarks</span></span>  
 <span data-ttu-id="ca9b4-108">이 메서드는 [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) 콜백 전에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca9b4-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca9b4-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca9b4-109">Requirements</span></span>  
 <span data-ttu-id="ca9b4-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca9b4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca9b4-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca9b4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca9b4-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca9b4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca9b4-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca9b4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

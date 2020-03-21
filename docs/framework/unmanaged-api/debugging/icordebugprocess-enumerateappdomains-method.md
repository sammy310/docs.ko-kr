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
ms.openlocfilehash: 4489238df05edef384b4073ee738a184ff8809ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178667"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="c5476-102">ICorDebugProcess::EnumerateAppDomains 메서드</span><span class="sxs-lookup"><span data-stu-id="c5476-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="c5476-103">이 프로세스의 모든 응용 프로그램 도메인을 모두 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c5476-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5476-104">구문</span><span class="sxs-lookup"><span data-stu-id="c5476-104">Syntax</span></span>  
  
``` cpp
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5476-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c5476-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="c5476-106">【아웃】 이 프로세스에서 응용 프로그램 도메인에 대 한 열거형 [ICorDebugAppDomainEnum의](icordebugappdomainenum-interface.md) 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c5476-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5476-107">설명</span><span class="sxs-lookup"><span data-stu-id="c5476-107">Remarks</span></span>  
 <span data-ttu-id="c5476-108">이 메서드는 [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) 콜백 전에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5476-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5476-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c5476-109">Requirements</span></span>  
 <span data-ttu-id="c5476-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5476-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5476-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5476-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5476-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5476-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5476-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5476-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

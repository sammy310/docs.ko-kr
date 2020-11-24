---
title: ICorDebugAppDomain::GetProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetProcess method [.NET Framework debugging]
ms.assetid: 9d0b9628-a91c-40d0-b9bc-00b34a396b8f
topic_type:
- apiref
ms.openlocfilehash: 6521341499df52c1851401f3f2f5c48a3b68ccd3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675960"
---
# <a name="icordebugappdomaingetprocess-method"></a><span data-ttu-id="3f465-102">ICorDebugAppDomain::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="3f465-102">ICorDebugAppDomain::GetProcess Method</span></span>

<span data-ttu-id="3f465-103">응용 프로그램 도메인을 포함 하는 프로세스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f465-103">Gets the process containing the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f465-104">구문</span><span class="sxs-lookup"><span data-stu-id="3f465-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f465-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f465-105">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="3f465-106">제한이 프로세스를 나타내는 ICorDebugProcess 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3f465-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f465-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f465-107">Requirements</span></span>  

 <span data-ttu-id="3f465-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f465-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f465-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f465-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f465-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f465-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f465-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f465-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

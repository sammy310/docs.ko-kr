---
description: '자세히 알아보기: ICorDebugAppDomain:: GetProcess 메서드'
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
ms.openlocfilehash: a681e58334df5dd7373e49b70c096fa1ff10773f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772408"
---
# <a name="icordebugappdomaingetprocess-method"></a><span data-ttu-id="0c249-103">ICorDebugAppDomain::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="0c249-103">ICorDebugAppDomain::GetProcess Method</span></span>

<span data-ttu-id="0c249-104">응용 프로그램 도메인을 포함 하는 프로세스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0c249-104">Gets the process containing the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c249-105">구문</span><span class="sxs-lookup"><span data-stu-id="0c249-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c249-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c249-106">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="0c249-107">제한이 프로세스를 나타내는 ICorDebugProcess 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0c249-107">[out] A pointer to the address of an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c249-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c249-108">Requirements</span></span>  

 <span data-ttu-id="0c249-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c249-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c249-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c249-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c249-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c249-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c249-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c249-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

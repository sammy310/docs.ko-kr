---
title: ICorDebugModule::GetProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetProcess method [.NET Framework debugging]
ms.assetid: 5e13446c-0271-446c-924a-9072c0e6eeae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97cecd66462cf6a88012b13dec82dbf617891dd5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988002"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="70c2f-102">ICorDebugModule::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="70c2f-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="70c2f-103">이 모듈의 포함 하는 프로세스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="70c2f-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70c2f-104">구문</span><span class="sxs-lookup"><span data-stu-id="70c2f-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70c2f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="70c2f-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="70c2f-106">[out] 이 모듈을 포함 하는 프로세스를 나타내는 ICorDebugProcess 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="70c2f-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70c2f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70c2f-107">Requirements</span></span>  
 <span data-ttu-id="70c2f-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="70c2f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70c2f-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70c2f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70c2f-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70c2f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70c2f-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70c2f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

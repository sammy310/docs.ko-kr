---
title: ICorDebugClass::GetModule 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e96d0d82b08449b4675ec7fd1517317006011ae
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478338"
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="03683-102">ICorDebugClass::GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="03683-102">ICorDebugClass::GetModule Method</span></span>
<span data-ttu-id="03683-103">이 클래스를 정의 하는 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="03683-103">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03683-104">구문</span><span class="sxs-lookup"><span data-stu-id="03683-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03683-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="03683-105">Parameters</span></span>  
 `pModule`  
 <span data-ttu-id="03683-106">[out] 이 클래스를 정의 하는 모듈을 나타내는 ICorDebugModule 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="03683-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03683-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="03683-107">Requirements</span></span>  
 <span data-ttu-id="03683-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="03683-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03683-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03683-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03683-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03683-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03683-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03683-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

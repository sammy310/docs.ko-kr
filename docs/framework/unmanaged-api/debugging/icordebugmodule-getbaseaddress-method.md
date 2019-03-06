---
title: ICorDebugModule::GetBaseAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetBaseAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11685e8ceba1638ce99a8c4c47b66d0ae2e67714
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476167"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="313c3-102">ICorDebugModule::GetBaseAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="313c3-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="313c3-103">모듈의 기본 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="313c3-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="313c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="313c3-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="313c3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="313c3-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="313c3-106">[out] `CORDB_ADDRESS` 모듈의 기본 주소를 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="313c3-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="313c3-107">설명</span><span class="sxs-lookup"><span data-stu-id="313c3-107">Remarks</span></span>  
 <span data-ttu-id="313c3-108">이 모듈은 네이티브 경우 (즉, 경우 모듈 네이티브 이미지 생성기, NGen.exe에서 생성 된) 이미지를 해당 기본 주소는 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="313c3-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="313c3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="313c3-109">Requirements</span></span>  
 <span data-ttu-id="313c3-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="313c3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="313c3-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="313c3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="313c3-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="313c3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="313c3-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="313c3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="313c3-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="313c3-114">See also</span></span>



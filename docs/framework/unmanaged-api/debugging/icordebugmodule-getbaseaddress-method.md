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
ms.openlocfilehash: aff8fb0a2316817e413f10e82215556f1f54fbc4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109633"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="3f02f-102">ICorDebugModule::GetBaseAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="3f02f-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="3f02f-103">모듈의 기본 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f02f-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f02f-104">구문</span><span class="sxs-lookup"><span data-stu-id="3f02f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f02f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f02f-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="3f02f-106">제한이 모듈의 기준 주소를 지정 하는 `CORDB_ADDRESS`입니다.</span><span class="sxs-lookup"><span data-stu-id="3f02f-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f02f-107">주의</span><span class="sxs-lookup"><span data-stu-id="3f02f-107">Remarks</span></span>  
 <span data-ttu-id="3f02f-108">모듈이 네이티브 이미지 (즉, 모듈이 네이티브 이미지 생성기, Ngen.exe에서 생성 된 경우) 인 경우 기본 주소는 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f02f-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f02f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f02f-109">Requirements</span></span>  
 <span data-ttu-id="3f02f-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f02f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f02f-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f02f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f02f-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f02f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f02f-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f02f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f02f-114">참조</span><span class="sxs-lookup"><span data-stu-id="3f02f-114">See also</span></span>

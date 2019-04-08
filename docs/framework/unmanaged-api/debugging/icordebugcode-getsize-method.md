---
title: ICorDebugCode::GetSize 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 678b7fbd595b1238b7025c22b0ed80b02ed4becd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085677"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="6de8b-102">ICorDebugCode::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="6de8b-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="6de8b-103">이 "ICorDebugCode"으로 표시 되는 이진 코드를 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6de8b-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6de8b-104">구문</span><span class="sxs-lookup"><span data-stu-id="6de8b-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6de8b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6de8b-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="6de8b-106">[out] 이 대 한 포인터의 크기 (바이트) 이진 파일의 코드 `ICorDebugCode` 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6de8b-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6de8b-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6de8b-107">Requirements</span></span>  
 <span data-ttu-id="6de8b-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6de8b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6de8b-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6de8b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6de8b-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6de8b-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6de8b-111">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="6de8b-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6de8b-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="6de8b-112">See also</span></span>

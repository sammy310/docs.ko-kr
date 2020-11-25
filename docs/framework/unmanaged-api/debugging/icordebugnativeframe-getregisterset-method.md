---
title: ICorDebugNativeFrame::GetRegisterSet 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type:
- apiref
ms.openlocfilehash: 945a398d32b50efc81ba45e705ed9d4161ed1524
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709273"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="1cf80-102">ICorDebugNativeFrame::GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="1cf80-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>

<span data-ttu-id="1cf80-103">이 스택 프레임에 대 한 레지스터 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1cf80-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cf80-104">구문</span><span class="sxs-lookup"><span data-stu-id="1cf80-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cf80-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1cf80-105">Parameters</span></span>  

 `ppRegisters`  
 <span data-ttu-id="1cf80-106">제한이 이 스택 프레임의 레지스터 집합을 나타내는 [ICorDebugRegisterSet](icordebugregisterset-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1cf80-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cf80-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1cf80-107">Requirements</span></span>  

 <span data-ttu-id="1cf80-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1cf80-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cf80-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1cf80-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1cf80-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1cf80-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1cf80-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cf80-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cf80-112">참조</span><span class="sxs-lookup"><span data-stu-id="1cf80-112">See also</span></span>

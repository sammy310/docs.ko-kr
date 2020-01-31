---
title: 'IcorDebugVariableHome:: GetLiveRange 메서드'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
ms.openlocfilehash: 28e41106ffcaf1ed2ed87166e641bb5e5f447e47
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791023"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="cc30d-102">IcorDebugVariableHome:: GetLiveRange 메서드</span><span class="sxs-lookup"><span data-stu-id="cc30d-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="cc30d-103">이 변수가 활성 상태인 기본 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc30d-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc30d-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc30d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc30d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc30d-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="cc30d-106">제한이 변수가 첫 번째 라이브 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="cc30d-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="cc30d-107">제한이 변수가 마지막으로 지속 된 지점 바로 다음의 논리적 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="cc30d-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc30d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc30d-108">Requirements</span></span>  
 <span data-ttu-id="cc30d-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc30d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc30d-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc30d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc30d-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc30d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc30d-112">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc30d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc30d-113">참조</span><span class="sxs-lookup"><span data-stu-id="cc30d-113">See also</span></span>

- [<span data-ttu-id="cc30d-114">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc30d-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
